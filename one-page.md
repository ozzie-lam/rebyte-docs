# Rebyte One Pager

Rebyte contains two things:
* **Revia**: An AI Assistant for your team members. You can think of it as a private Chatgpt with your team's private knowledge and workflow.
* **Builder Platform**: Builder in your team can capture your team's proprietary knowledge and workflow, and make them available to **Revia**.

## Revia
**Revia** is a universal user interface that can be used by all team members to interact with the AI assistant. This interface is designed to handle various types of tasks, such as data retrieval, question and answer, document generation, and data analysis, and more advanced tasks such as interactive chart and table, form filling and more.

Besides Revia, team admin can build other assistants specific to some use cases, for example, a customer support assistant, a sales assistant, a marketing assistant, etc.

The relationship between **Revia** and **Other Assistants** is like the relationship between **ChatGpt** and **Gpts**.

## Builder Platform
Only builders or admin in your team can access the builder platform. Those are main components in the builder platform:
* **Actions**: represent a single unit of work that tool can perform, such as make a LLM call, read a file, or generate a document, run piece of code, call external services etc. Actions can be chained together to form a sequence of actions that the tool will perform.
* **Tools**: a no-code UI for capturing proprietary workflow, it represents a sequence of actions.
* **Knowledge** : a data pipeline for aggregating data from various enterprise sources, embedding them, and making them available to tools.
* **API**: all mentioned above can be accessed via API, so you can integrate Rebyte with your existing systems.
