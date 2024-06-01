# Input

* The `Input Action` is used to send input information to the Agent. Other actions are based on the input information to perform the right operation.

* The first action in the Agent must be an `Input Action`, you can not delete it or copy it.

* In Design mode, you can specify a dataset as INPUT, each data in this dataset(each row) will be considered as a separate input to agent, and all inputs will be run in parallel. Each data row will receive a separate thread id.

* In production mode, input are passed via agent API.

* Rebyte defines a common data structure to handle messages passed into agent, it's strong recommended to use this format in order to make your agent work with assistant/thread API seamlessly.

## Common Message Format

```json
{
  "role": "role of this message, for example user, assistant",
  "content": "content string of this messages",
  "parts": [
    {
      "type": "image_url",
      "image_url": {
        "url": "url of this image"
      }
    },
    {
      "type": "file",
      "file": {
        "id": "uuid of this file",
        "name": "name of this file, with extension"
      }
    }
  ]
}
```

if your agent wants to handle list of messages, use following format:
```json
{
  "messages": [
    {
      "role": "",
      "content": ""
    },
    {
      "role": "",
      "content": ""
    }
  ]
}
```

**IMPORTANT**
Only messages conform to this format will be saved to thread automatically, other messages will be ignored

## Usage

You can use the input by using the `{{INPUT.message}}` variable in the instructions or `env.state.INPUT.messages` in the code editor.

<figure><img src="../../../images/input-action.png"></figure>

## Data Format

* When used in agent page, the input is extracted from the predefined datasets.

* When connected to Apps, the input is from the app user's input and conversation history. By default, We will put the last 10 messages to the agent.

* The input data format is as follows:

    ```json
    {
    "messages":[{
            "role": "user",
            "content": "The content."
        },
        {
            "role": "assistant",
            "content": "The content."
        }]
    }
    ```

<!-- ### Parameters

- Input type
    - Select from predefined Datasets
    - When connecting to Chat, the latest 10 history dialogues will be sent to the Agent as input information by default, formatted as follows
    
    ```json
    {
    "Messages":[
    {
        "role": "user",
        "content": "The content."
    },
    {
        "role": "assistant",
        "content": "The content."
    }
    ]
    }
    ```
    - output
        - Output the correct data -->