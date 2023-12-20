# LLM Chat

### spec

| Parameter   | Description          |
| ----------- | -------------------- |
| Instruction | The system message   |
| Messages    | Messages send to LLM |

Messages can be a list of strings or a list of objects. If it is a list of objects, each object must have a `content` field. The `content` field is the message to be sent to the LLM. The object can also have a `role` field, which is the role of the message, allowed values are `user`, `assistant` and `system`.

### config

| Parameter   | Description                              |
| ----------- | ---------------------------------------- |
| max\_tokens | The maximum number of tokens to generate |
| temperature | What sampling temperature to use         |

### Message format

Rebyte uses similar message format as OpenAI. The message format is a JSON object with the following fields:

| Parameter         | Description                                          |
| ----------------- | ---------------------------------------------------- |
| role              | could be 'user', 'system', or 'assistant'            |
| content           | content of this message                              |
| name(optional)    | name of role                                         |
| context(optional) | context of this message, for example, external file. |

#### Example

simple message


```json
{
    "content": "Hello, how are you?",
    "role": "user"
    "name": "meowoof"
    "context": {
        "files": [
    {
                "uuid": "f3610fef-f490-4675-81fe-df04735f5058",
                "name": "file1.pdf"
            },
            {
                "name": "f3610fef-f490-4675-81fe-df04735f5059",
                "content": "file2.txt"
            }   
    }
}
```



list of messages


```json
[
    {
        "content": "You're talking to a chatbot!",
        "role": "system"
    },
    {
        "content": "Hello, how are you?",
        "role": "user"
        "name": "meowoof"
    },
    {
        "content": "I am fine, thank you.",
        "role": "assistant"
        "name": "rebyte"
    },
    {
        "content": "what's your plan today?",
        "role": "user"
        "name": "meowoof"
    }
]
```

<!-- ### example

* [LLM chat](https://rebyte.ai/p/21b2295005587a5375d8/callable/719d2f31bf9fe977f699) -->
