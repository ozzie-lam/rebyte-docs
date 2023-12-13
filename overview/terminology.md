### Terminology

- **Agent**: A serverless function that can be executed on ReByte runtime.
- **Action** Building blocks of LLM agents; each agent consists of a sequential list of actions.
- **Knowledge**: A private data ingestion pipeline that can be used by LLM agents.
- **Agent UI Builder**: A user interface builder that enables developers to connect LLM agents and knowledge to create their own tools.
- **External files**: These are files not stored within ReByte knowledge but can be utilized by an LLM agent. For example, in an agent that performs resume analysis, the resume file is considered an external file.
- **ReByte Team**: A concept that allows multiple users to collaborate on the same knowledge and agent, and also enforces access control. A team can have multiple members, with each member having different levels of access. Each login user is assigned one default team, named after the user's display name.
- **API Key**: A secret token that enables developers to call an agent via an HTTP API. Each team has its own API Key, which grants access to all agents and knowledge associated with that team.
- **Credential** Manage developers' credential for third party services, such as GitHub API token. Credential can be used in LLM agent to access third party services without exposing the secret token in the agent specification.
- **JsBundle**: A special type of action that allows developers to write their own JavaScript code and submit it to the ReByte Action Hub.
- **Rebyte CLI**: A command-line tool that enables developers to build and deploy customized JsBundles.
- **Action Hub**: A marketplace for JsBundles where developers can submit their JsBundles, and other users can incorporate them into their LLM agents.