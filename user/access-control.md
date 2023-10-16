## Visibility and Access Control

Rebyte is built with fine-grained access control from day one. You can control the visibility of your agents, data, app, and other resources in Rebyte. We believe this is critical to enable collaboration and sharing AI applications in enterprise environments.

### Project(aka Team)
Access control is based on project, or team. Project or team are same thing in Rebyte. We may interchangeably use these two terms in this document.
There are two types of projects in Rebyte:
**personal** vs **team** project. Personal project is created when a user is created, it's private to the user. Team project is created by a user, it's shared among team members.

### Resource
Following resources can be controlled by access control:
* Agent
* Knowledge
* App

### Visibility
There are three visibility options for each resource:
public/private/unlisted.

Depending on context, the actual meaning of these three options are every different

### Role
There are three roles in Rebyte Project:
* **Owner**: Owner has full access to the project, including creating new agents, knowledge, and apps. Owner can also invite new members to the project, generate API keys, and delete the project.
* **Builder**: Builder can create new agents, knowledge, and apps. Builder can see all public/private/unlisted resources in the project. Builder can also invite new members to the project, generate API keys.
* **User** User can only view the public resources in the project. User can use the agent, knowledge, and apps in the project. 
