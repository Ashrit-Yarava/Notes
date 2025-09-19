---
tags:
  - llm
  - java
---
Add the following to the maven `pom.xml` and specify the `${openai.version}` in the `<properties>`:
```xml
<dependency>  
	<groupId>com.openai</groupId>  
	<artifactId>openai-java</artifactId>  
	<version>${openai.version}</version>  
</dependency>
```
## Code
```java
import com.openai.client.OpenAIClient;  
import com.openai.client.okhttp.OpenAIOkHttpClient;  
import com.openai.models.ChatModel;  
import com.openai.models.chat.completions.ChatCompletion;  
import com.openai.models.chat.completions.ChatCompletionCreateParams;  
import org.slf4j.Logger;  
import org.slf4j.LoggerFactory;  
  
import java.util.List;  
import java.util.Optional;  
  
public class Llm {  
  
    Logger logger;  
    OpenAIClient client;  
    String systemPrompt;  
    List<String> history;  
  
    public Llm(String systemPrompt) {  
        logger = LoggerFactory.getLogger(Llm.class);  
        client = OpenAIOkHttpClient.builder().fromEnv().build();  
  
        this.systemPrompt = systemPrompt;  
    }  
  
    public String call() {  
        ChatCompletionCreateParams.Builder paramsBuilder = ChatCompletionCreateParams.builder();  
  
        paramsBuilder.addSystemMessage(this.systemPrompt);  
  
        // Add the prior interactions between the user and the agent.  
        boolean userTurn = true;  
        for (String message : this.history) {  
            if (userTurn) {  
                paramsBuilder.addUserMessage(message);  
            } else {  
                paramsBuilder.addAssistantMessage(message);  
            }  
            userTurn = !userTurn;  
        }  
  
        // Add which model to use.  
        paramsBuilder.model(ChatModel.GPT_3_5_TURBO);  
  
        // Generate the model output.  
        ChatCompletionCreateParams params = paramsBuilder.build();  
        ChatCompletion completion = this.client.chat().completions().create(params);  
        Optional<String> message = completion.choices().get(0).message().content();  
  
        if (message.isPresent()) {  
            return message.get();  
        }  
  
        this.logger.error("Failed to generate llm output.");  
        return "";  
    }  
  
}
```