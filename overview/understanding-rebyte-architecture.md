# 💡 ReByte Concepts

<figure><img src="../.gitbook/assets/Screenshot 2023-10-08 at 6.10.41 PM.png" alt=""><figcaption></figcaption></figure>

> Subroutine for your AI application.

* LLM Serverless Agent is a piece of sequential actions that can be executed on the LLM serverless runtime. It is the core building block of ReByte, and the main way for end users to create their own tools. Rebyte provides a GUI builder for end users to create/edit their own LLM agents. Rebyte provides a list of pre-built actions for common use cases, also private SDK for _software engineer_ to build their own actions, and seamlessly integrate with the agent builder. Pre-built actions includes:
  * LLM Actions
    * Language Model Completion Interface
    * Language Model Chat Interface
  * Data Actions
    * Dataset Loader, load pre defined datasets for later processing
    * File Loader, extract/transform/load user's provided files
    * Semantic Search, search for similar content over user's knowledge base
  * Tools Actions
    * Search Engine, search for information on Google/Bing
    * Web Crawler, crawl web pages and extract information
    * Http Request Maker, make any http request to any public/private API
  * Control flow Actions
    * Loop Until, run actions until a condition is met
    * Parallel, execute multiple actions in parallel
    * Vanilla Javascript, execute any vanilla javascript code, useful for doing pure data transformation
  * Customized JsBundle(private beta)
    * Software engineer can build their own JsBundle and submit to ReByte **Action MarketPlace**, so that end users can use it in their agents. JsBundle can use any npm packages, so greatly expand the capability of LLM agents.

## Knowledge - capture private data

> Ingredient for your AI application.

* Knowledge is private data that is stored in rebyte managed vector database. Rebyte currently provides following connectors for end users to import their knowledge:
  * Local file, supported file types are:
    * "doc", "docx", "img", "epub", "jpeg", "jpg", "png", "xls", "xlsx", "ppt", "pptx", "md", "txt", "rtf", "rst", "pdf", "json", "html",
  * Notion
  * Discord
  * GitHub
  * More connectors are coming soon
* Knowledge can be used in LLM Agents to do semantic search, or to do data augmentation. A great example is to use knowledge to do semantic search on a user's private knowledge base, and use the search result to do data augmentation for a language model, aka **Retrieval Augmented Generation**.

## Agent UI builder

* UI layer is the end user facing part of rebyte, it is a universal UI interface/protocol that allows user to wire up LLM Agents and knowledge to create their own tools.
  * A universal UI builder for lightweight tools
  * Automatically wire up multiple LLM Agents and knowledge
  * Fully hosted and managed by ReByte

## ReByte Runtime

All Rebyte Agents are executed on ReByte Runtime, which is a serverless function runtime that serves similar functionality as AWS Lambda.
