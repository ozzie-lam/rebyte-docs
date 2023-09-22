# Language Model Completion Interface

This action directly maps the call to the LLM API completion interface. For more information on the API detail, see the [OpenAI API documentation](https://platform.openai.com/docs/api-reference/completions/create). Most other LLMs also support this interface.

Currently, the LLM Completion Interface only supports the following parameters:

| Parameter | Description                              |
|---|------------------------------------------|
| prompt | The prompt to be sent to the model       |
| max_tokens | The maximum number of tokens to generate |
| temperature | What sampling temperature to use         |
