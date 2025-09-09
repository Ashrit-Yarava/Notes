---
tags:
  - system
  - llm
---
The server has a couple of GPUs that are available for use. The command below sets up a llama-server that can be used with the OpenAI api.
```bash
./build/bin/llama-server -dev CUDA0,CUDA1,CUDA2,CUDA3 -ngl 35 -m <model file> --alias model
```
The above command uses the four available devices, which can be checked with:
```bash
./build/bin/llama-server --list-devices
```
Then when using the openai api, connect with `base_url="http://<host>:<port>/v1/"` and any API key.