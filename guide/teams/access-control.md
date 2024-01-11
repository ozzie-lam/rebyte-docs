# Access Control

Rebyte is built with fine-grained access control. You can control the visibility of your agents, knowledge, apps and other resources in Rebyte. We believe that this is of vital importance for collaboration and sharing AI applications in enterprise environments.

## Types of Accounts

In Rebyte, there are two types of accounts: Personal and Team.

We have designed corresponding permission rules for the core functions of the Rebyte system: agent, knowledge, and app.

## Personal Accounts

Personal accounts are for individual users, who can develop agents and applications the way they like and use applications in the Rebyte community.

For personal accounts, upgrading to a "pro" account allows the sharing of agents, knowledge, and apps with other users so that they can view and use.

Sharing an agent means others can view the agent you have created, including its workflow and datasets. However, they cannot run or modify it. If another user wants to use it, they can clone the agent into their own account to run and make adjustments.

Sharing knowledge allows other users to view the content in your knowledge base.

Sharing an app allows other users to use the app you have built.

Further details are available in the following table:

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

## team accounts

Team accounts allows for collaboration among teams, and there are three roles in a team account.

* Builders (builder, admin, owner): develop and maintain the team's agents, knowledge, and apps.

* Users: use applications within the team.

* Non-team users: users who are not part of the team.

For team accounts, builders can develop, design, and use the agents, knowledge, and apps within the team account. Users can view and use the apps, knowledge, and agents in the team account.

Regarding agents, users can view all agents' workflows and datasets within the team and can copy them to their personal accounts to modify and run. When an agent is set to External Unlisted, users outside the team can use a link to view the agent. When an agent is set to Public, it appears in the team agent list for external users.

Regarding knowledge, it can be set so only admins and owners can create knowledge, while builders can maintain it. External Public set knowledge can be viewed by users outside the team.

Regarding apps, there are four access-levels. Private apps can only be seen by builders, which is useful for maintaining apps that are still under development.team Unlisted apps can be accessed and used by team users via a link. Apps set to Team Public can be viewed and used by all team members on the team app page. External Public means that users outside the team can also view and use the app.

For example, in an administrative team, the owner and admin manage the team's resources, builders are responsible for designing and building agents, knowledge, and apps. And users are responsible for viewing and using the agents, knowledge, and apps designed by the builders. When an app is not yet complete, a builder can set its access-level to Private. Once the design is finished, it can be set to Team Public for team members to use. Setting it to External Public allows sharing with users outside the team.

Further details are available in the following table:

| Team-Access       | Non-team user        | Team user（member）               | Team Builder（admin、owner）      |      |
| ----------------- | -------------------- | --------------------------------- | --------------------------------- | ---- |
| Team-App          |                      |                                   |                                   |      |
| Private           |                      |                                   | list,use,edit,create              |      |
| team Unlisted     |                      | Use with link                     | list,use,edit,create              |      |
| team Public       |                      | list,use                          | list,use,edit,create              |      |
| External Public   | list,use             | list,use                          | list,use,edit,create              |      |
| Team-Knowledge    |                      |                                   |                                   |      |
| External Public   | list,use             | list,use                          | list,use,edit,create(admin&owner) |      |
| team Public       |                      | list,use                          | list,use,edit,create(admin&owner) |      |
| Team-Agent        |                      |                                   |                                   |      |
| team Public       |                      | list,view（design,dataset）,clone | list,view,edit,create             |      |
| External Unlisted | view,clone with link | list,view,clone                   | list,view,edit,create             |      |
| External Public   | list,view,clone      | list,view,clone                   | list,view,edit,create             |      |
