# Language Model Chat

## Usage

We provide a simple `Language Model Chat` action for you to chat with the large language model. 

Simply, you just need to write your specifications and configure the model, and the large language model will generate the response.

### Specification

<!-- | Parameter   | Description          |
| ----------- | -------------------- |
| Instruction | The system message   |
| Messages    | Messages send to LLM |
| Fuctions    |      hahaha          | -->

**Instruction**
* This is the message that will be sent to the model. 
* Write your prompt here and tell the large language model what to do.

**Messages**
* This is the messages that will be sent to the LLM. 
* You can refer to the output of other actions here using Javascript or Tera format.
* Messages can be a list of strings or list of objects. If it's a list of objects, make sure each object has a `role` field as well as a `content` field.:
  * The `role` field specifies the role of the message, allowed roles are `user`, `assistant` and `system`.
  * The `content` contains the message to be sent to the model.

**Functions**
* This is the functions that will be sent to the LLM.

### Configuration

You can choose the model you want to use by clicking the model's name.

<figure><img src="../../../../images/chat-models.png"></figure>

Click this button in the bottom right corner of the `Language Model Chat` action to open the configuration panel.

<figure><img src="../../../../images/chat-config-button.jpg"></figure>

There are five settings in the configuration panel, as shown below.

<figure><img src="../../../../images/chat-config-2.png"></figure>

<!-- | Parameter    | Description                              |
| ------------ | ---------------------------------------- |
| max\_tokens  | The maximum number of tokens to generate |
| temperature  | What sampling temperature to use         |
| JSON response|                                          |
| Seed         |                                          |
| Stop words   |                                          | -->

**Temperature**
  * "Temperature" controls the randomness of the model's output.
  * The higher the model temperature, the more random the output is.
  
**Maximum Output Tokens**
  * "Maximum Output tokens" specifies the maximum number of tokens to generate.
  * Can use up to 40,000 tokens(the limit for models vary), including prompt and model returned content.
  
**JSON Response**
  * "JSON Response" button enable JSON mode, which guarantees the messages the model generate are in JSON format.
  * NOTE: This feature is a beta feature and only supported by OpenAI's "gpt-4-1106-preview" model now.

**Seed**
  * The "Seeds" is a parameter that can be specified when using the `Language Model Chat` and `Language Model Completion` actions. 
  * It helps to ensure consistent outputs by making the system sample deterministically, resulting in the same result for repeated requests with the same seed and parameters.
  * NOTE: This feature is a beta feature and may not be supported by all models.

**Stop Words**
  * Stop words are used to make the model stop at a desired point, such as the end of a sentence or a list. 

### Message Format

Rebyte uses a similar message format as OpenAI. The message format is a JSON object with the following fields:

* role
  * could be one from 'user', 'system', or 'assistant'
* content
  * content of this message
* name(optional)
  * name of role
* context
  * context of this message, for example, external file

On the top right of the action, there are two more things to configure: "Stream Mode" and "Cache Mode".

<figure><img src="../../../../images/stream-and-cache.jpg"></figure>


**Stream**
* This option allows you to receive partial chat responses as they are being generated, rather than waiting for the entire completion to be finished before receiving a response.

* By setting stream mode, you can start processing or displaying the beginning of the chat before the full response is received.

**Cache**

* Caching involves storing frequently accessed data to improve response times without making repeated calls to a model. 
* If you use the cache mode, the model will cache the response and return the cached response when the same request is made again. This will make your agent run faster.


<!-- | Parameter         | Description                                          |
| ----------------- | ---------------------------------------------------- |
| role              | could be 'user', 'system', or 'assistant'            |
| content           | content of this message                              |
| name(optional)    | name of role                                         |
| context(optional) | context of this message, for example, external file. | -->

**Message Format Examples**

1.Simple message

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



2.List of messages


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

## Example Agent

* [LLM Chat](https://rebyte.ai/p/21b2295005587a5375d8/callable/719d2f31bf9fe977f699/editor)