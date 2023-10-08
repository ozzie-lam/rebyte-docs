# Language Model Completion Interface

This action directly maps the call to the LLM API completion interface. Rebyte current supports the following model providers:

#### OpenAI
For more information on the API detail, see the [OpenAI API documentation](https://platform.openai.com/docs/api-reference/completions/create).

#### Anthropic

[Anthropic API documentation](https://docs.anthropic.com/claude/docs).

#### LLAMA2

[LLAMA2](https://app.endpoints.anyscale.com/)



### spec
| Parameter | Description                              |
|---|------------------------------------------|
| prompt | The prompt to be sent to the model       |

### config

| Parameter | Description                              |
|---|------------------------------------------|
| max_tokens | The maximum number of tokens to generate |
| temperature | What sampling temperature to use         |

