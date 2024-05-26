ReByte provides a set of APIs to make it easy to integrate ReByte into your own applications. There're three main APIs: File API, Agent API, and Thread API. 

## Agent API

Agent API allows you to call the agent you created on ReByte. It supports:

* blocking and non-blocking calls
* streaming
* specifying agent version
* specify config of action within agent

## Thread API

Thread API allows you to create a conversation thread and add messages to the thread. Combined with the Agent API, you can create an agent with memory without having your own backend.

## File API
File API allows you to upload files to ReByte. Uploaded files can be used in the agent's actions, such as `File Loader` action.