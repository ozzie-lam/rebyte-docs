# Access Control

Rebyte is built with fine-grained access control from day one. You can control the visibility of your agents, data, app, and other resources in Rebyte. We believe this is critical to enable collaboration and sharing AI applications in enterprise environments.

## Team

Access control is based on project, or team. Project or team are same thing in Rebyte. We may interchangeably use these two terms in this document. There are two types of projects in Rebyte: **personal** vs **team** project. Personal project is created when a user is created, it's private to the user. Team project is created by a user, it's shared among team members.

## Resource

Following resources can be controlled by access control:

* Agent
* Knowledge
* App

## Visibility

There are three visibility options for each resource: public/private/unlisted.

Depending on context, the actual meaning of these three options are every different

## Role

There are four roles in Rebyte Project:

* **None** Any login user will automatically have this role in all projects. This role is used to indicate the user is not a member of the project.
  * **use public app**
  * **view public agent**
  * **view public knowledge**
  * **use unlisted app**
  * **view unlisted agent**
* **User** User can only view the public resources in the project. User can use the agent, knowledge, and apps in the project.
  * **list public/private/unlisted agent**
  * **list public/private knowledge**
  * **list public/private/unlisted app**
* **Builder**: Builder can create new agents, knowledge, and apps. Builder can see all public/private/unlisted resources in the project. Builder can also invite new members to the project, generate API keys.
  * **create new agent**
  * **create new knowledge**
  * **create new app**
  * **can invite new members**
  * **see invite link**
  * **generate API keys**
  * **Deploy agent**
  * **See all traces of the agent**
* **Owner**: Owner has full access to the project, including creating new agents, knowledge, and apps. Owner can also invite new members to the project, generate API keys, and delete the project.
  * **transfer owner to other users**



<table data-header-hidden data-full-width="true"><thead><tr><th width="330"></th><th width="141"></th><th width="130"></th><th width="143"></th><th width="131"></th><th></th></tr></thead><tbody><tr><td>Access</td><td>Personal user</td><td>Team User</td><td>Team Builder</td><td>Team Admin</td><td>Team Owner</td></tr><tr><td>list public apps of unjoined teams and other personal projects</td><td>✔</td><td>✔</td><td>✔</td><td>✔</td><td>✔</td></tr><tr><td>list all apps in personal projects</td><td>✔</td><td><br></td><td><br></td><td><br></td><td><br></td></tr><tr><td>list all apps of joined teams</td><td><br></td><td>✔</td><td>✔</td><td>✔</td><td>✔</td></tr><tr><td>use public app</td><td>✔</td><td>✔</td><td>✔</td><td>✔</td><td>✔</td></tr><tr><td>use unlisted app with link</td><td>✔</td><td>✔</td><td>✔</td><td>✔</td><td>✔</td></tr><tr><td>use private apps of teams</td><td><br></td><td>✔</td><td>✔</td><td>✔</td><td>✔</td></tr><tr><td>create/update apps in personal projects</td><td>✔</td><td><br></td><td><br></td><td><br></td><td><br></td></tr><tr><td>create/update apps in joined teams</td><td><br></td><td><br></td><td>✔</td><td>✔</td><td>✔</td></tr><tr><td>list public knowledges of unjoined teams and other personal projects</td><td>✔</td><td>✔<br></td><td>✔</td><td>✔</td><td>✔<br></td></tr><tr><td>list all knowledges in personal projects</td><td>✔</td><td><br></td><td><br></td><td><br></td><td><br></td></tr><tr><td>list all knowledges of joined teams</td><td><br></td><td>✔</td><td>✔</td><td>✔</td><td>✔</td></tr><tr><td>View public knowledge</td><td>✔</td><td>✔</td><td>✔</td><td>✔</td><td>✔</td></tr><tr><td>View private knowledge of teams</td><td><br></td><td>✔</td><td>✔</td><td>✔</td><td>✔</td></tr><tr><td>create/update knowledges in personal projects</td><td>✔</td><td><br></td><td><br></td><td><br></td><td><br></td></tr><tr><td>create/update knowledges in joined teams</td><td><br></td><td><br></td><td>✔</td><td>✔</td><td>✔</td></tr><tr><td>list public agents of unjoined teams and other personal projects</td><td>✔</td><td>✔</td><td>✔</td><td>✔</td><td>✔</td></tr><tr><td>list all agents in personal projects</td><td>✔</td><td><br></td><td><br></td><td><br></td><td><br></td></tr><tr><td>list all agents of joined teams</td><td><br></td><td>✔</td><td>✔</td><td>✔</td><td>✔</td></tr><tr><td>View and clone public agents</td><td>✔</td><td>✔</td><td>✔</td><td>✔</td><td>✔</td></tr><tr><td>View and clone unlisted agents with link</td><td>✔</td><td>✔</td><td>✔</td><td>✔</td><td>✔</td></tr><tr><td>View private agents of teams</td><td><br></td><td>✔</td><td>✔</td><td>✔</td><td>✔</td></tr><tr><td>create/update/dev/debug/deploy agents in personal projects</td><td>✔</td><td><br></td><td><br></td><td><br></td><td><br></td></tr><tr><td>create/update/dev/debug/deploy agents in joined teams</td><td><br></td><td><br></td><td>✔</td><td>✔</td><td>✔</td></tr><tr><td>generate/manage team‘s API keys</td><td><br></td><td><br></td><td>✔</td><td>✔</td><td>✔</td></tr><tr><td>create/manage credentials</td><td><br></td><td><br></td><td>✔</td><td>✔</td><td>✔</td></tr><tr><td>invite new members to team</td><td><br></td><td><br></td><td><br></td><td>✔</td><td>✔</td></tr><tr><td>generate and see invite link</td><td><br></td><td><br></td><td><br></td><td>✔</td><td>✔</td></tr><tr><td>set builder</td><td><br></td><td><br></td><td><br></td><td>✔</td><td>✔</td></tr><tr><td>set admin</td><td><br></td><td><br></td><td><br></td><td>✔</td><td>✔</td></tr><tr><td>revoke member</td><td><br></td><td><br></td><td><br></td><td>✔</td><td>✔</td></tr><tr><td>transfer owner to other users</td><td><br></td><td><br></td><td><br></td><td><br></td><td>✔</td></tr></tbody></table>
