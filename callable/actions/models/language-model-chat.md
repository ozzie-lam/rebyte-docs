# Language Model Chat Interface

This action directly maps the call to the LLM API chat interface. For more information on the API detail, see the [OpenAI API documentation](https://beta.openai.com/docs/api-reference/chat).

Currently, the LLM Chat Interface only supports the following parameters:

| Parameter   | Description                              |
|-------------|------------------------------------------|
| Instruction | The system message                       |
| Messages    | Messages send to LLM                     |
| max_tokens  | The maximum number of tokens to generate |
| temperature | What sampling temperature to use         |

Messages can be a list of strings or a list of objects. If it is a list of objects, each object must have a `content` field. The `content` field is the message to be sent to the LLM. The object can also have a `role` field, which is the role of the message, allowed values are `user`, `assistant` and `system`.

