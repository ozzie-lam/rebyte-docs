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

Depending on context, the actual meaning of these three options are different.

See more about agent/app and knowledge visibility in [Visibility](./visibility.md).

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

| Team-Access     | Non-team user        | Team user（member）               | Team Builder（admin、owner） |
| --------------- | -------------------- | ------------------------------- | ------------------------- |
| Team-App        |                      |                                 |                           |
| Private         |                      |                                 | list,use,edit,create      |
| Unlisted        |                      | Use with link                   | list,use,edit,create      |
| team Public     |                      | list,use                        | list,use,edit,create      |
| External Public | list,use             | list,use                        | list,use,edit,create      |
| Team-Knowledge  |                      |                                 |                           |
| Public          | list,use             | list,use                        | list,use,edit,create      |
| Private         |                      | list,use                        | list,use,edit,create      |
| Team-Agent      |                      |                                 |                           |
| Private         |                      | list,view（design,dataset）,clone | list,view,edit,create     |
| Unlisted        | view,clone with link | list,view,clone                 | list,view,edit,create     |
| Public          | list,view,clone      | list,view,clone                 | list,view,edit,create     |

| Personal-Access | Other users          | Personal user        |
| --------------- | -------------------- | -------------------- |
| App             |                      |                      |
| Private         |                      | list,use,edit,create |
| Public          | list,use             | list,use,edit,create |
| Knowledge       |                      |                      |
| Public          | list,view            | list,use,edit,create |
| Private         |                      | list,use,edit,create |
| Agent           |                      |                      |
| Public          | list,view,clone      | list,use,edit,create |
| Unlisted        | view,clone with link | list,use,edit,create |
| Private         |                      | list,use,edit,create |
