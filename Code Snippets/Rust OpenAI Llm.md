---
tags:
  - llm
  - rust
---
The implementation below acts as an interface for the OpenAI api for rust. The algorithm is capable of storing previous prompts upon request.
```rust
use openai_api_rust::chat::{ChatApi, ChatBody};
use openai_api_rust::models::ModelsApi;
use openai_api_rust::{Auth, Message, OpenAI, Role};
use std::collections::HashMap;

pub struct Llm {
    model: String,
    max_tokens: i32,
    openai: OpenAI,
    cache: HashMap<String, String>, // Keep track of prior outputs.
    session: Vec<Message>,
}

/// A simple wrapper around the OpenAI api that allows for storing the previous interactions for more robust prompting.
impl Llm {
    /// Create a new instance of the OpenAI LLM with the given URL endpoint.
    /// The endpoint should be in the format:
    /// http://<host>:<port>/v1/
    pub fn new(max_tokens: i32, _url: Option<String>) -> Self {
        let url = _url.expect("http://localhost:8800/v1/");
        let openai = OpenAI::new(Auth::new("Bonita"), &url);

        let models = openai.models_list().expect("Failed to get models.");
        let model = models.get(0).unwrap().id.to_string();
        let cache = HashMap::new();
        let session = Vec::new();

        Llm {
            model,
            max_tokens,
            openai,
            cache,
            session,
        }
    }

    /// Generate the LLM response for the given prompt. If `store` is true, then the prompt is stored and used (useful for caching).
    /// The if store is not true, then the prompt is given to the model along with the text from the current session.
    pub fn completion(&mut self, prompt: &str, store: bool) -> String {
        if self.cache.contains_key(prompt) {
            return self.cache.get(prompt).expect("").to_owned();
        }

        // Get the completion only if there is no prior context.
        let mut messages = Vec::new();
        for message in self.session.iter() {
            messages.push(message.to_owned());
        }
        messages.push(Message {
            role: Role::User,
            content: prompt.to_owned(),
        });

        let body = ChatBody {
            model: self.model.to_owned(),
            max_tokens: Some(self.max_tokens), // Define the max number of tokens.
            temperature: Some(0_f32),
            top_p: Some(0_f32),
            n: Some(1),
            stream: Some(false),
            stop: None,
            presence_penalty: None,
            frequency_penalty: None,
            logit_bias: None,
            user: None,
            messages,
        };
        let output = self
            .openai
            .chat_completion_create(&body)
            .expect("Failed to retrieve message from server.");
        let message = output
            .choices
            .get(0)
            .unwrap()
            .message
            .to_owned()
            .expect("Failed to retrieve message from output.")
            .content;

        if store {
            self.cache.insert(prompt.to_owned(), message.clone());
        }

        // Add the model output to the session.
        self.session.push(Message {
            role: Role::Assistant,
            content: message.to_owned(),
        });

        message
    }

    /// Clear the prior messages in the session.
    pub fn clear_session(&mut self) {
        self.session.clear();
    }
}
```