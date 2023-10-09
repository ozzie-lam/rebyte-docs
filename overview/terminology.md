### Terminology

- **Agent**: A serverless function that can be executed on ReByte runtime.
- **Action** buidling block of LLM agent, each agent is a sequential list of actions.
- **Knowledge**: Private data ingestion pipeline that can be used in LLM agent.
- **Agent UI Builder**: User interface builder that allows developer to wire up LLM agents and knowledge to create their own tools.
- **External files** are files that are not stored in ReByte knowledge, but can be used in LLM agent. For example agent that does resume analysis, the resume file is an external file.
- **Rebyte User** login user of ReByte.
- **ReByte Team**: Team is a concept that allows multiple users to collaborate on the same knowledge and agent, also enforce access control. Team can have multiple members, and each member can have different access level. Each login user has one default team, named after the user's display name.
- **API Key** is a secret token that allows developer to call Agent via http API. Each team has its own API Key. Each API key can access all agents and knowledge that belongs to the team.
- **Credential** Manage developers' credential for third party services, such as GitHub API token. Credential can be used in LLM agent to access third party services without exposing the secret token in the agent specification.
- **JsBundle** is a special type of action that allows developer to write their own javascript code and submit to ReByte Action Hub.
- **Rebyte CLI** is a command line tool that allows developer to build and deploy customized JsBundle.
- **Action Hub** is a marketplace for JsBundle, where developer can submit their JsBundle and end user can use it in their LLM agents.
