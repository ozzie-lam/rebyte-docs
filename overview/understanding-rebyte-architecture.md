# 💡 Understanding ReByte Architecture

## How ReByte work

**ReByte** can be seen as having three layers

* **Callable:** The infrastructure that handles all LLM-based workflows. It follows serverless function architecture (like AWS Lambda) that enables maximum scalability&#x20;
* **Knowledge:** Managed vector database for fast information retrieval and near real-time syncing
* **Client Interface**
  * **Copilot:** is a managed UI that enables end-users to conveniently interact with AI applications
  * **API:** API and SDK clients are provided to support developers who wish to directly interact with their callables to power their own products


### A Basic Workflow

When the end user interacts with a **Copilot**, a few things happen in the background:

1. ReByte Copilot client compiles users' input into a standard format defined by its UI standard protocol and includes session history. Since Callable is designed to be stateless and serverless, the copilot server will be responsible to store the history.&#x20;
2. The Copilot client sends an API request to a specific Callable
3. The Callable is triggered and performs its predefined programming.&#x20;
   1. The Callable interacts with Knowledge to retrieve relevant information
   2. The Callable sends requests to the language model services
4. The Callable returns a response in a predefined format to Copilot, and Copilot displays the messages to users.

