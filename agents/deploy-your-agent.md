# Deploy Your Tool

Once you have finished designing and testing your agent, click "Deploy" to publish a new version or checkout the current version.

## Versioning

Correct versioning is extremely important for tracking changes and ensuring that your agent is working as expected.

### Rules

* Each deployment will receive a new version number, starting from 1
* You can specify the version number when calling the agent
* Use special version number 'latest' to call the latest version of the agent
* Each agent can have a 'live' version, which may be different from the latest version. A typical use case is to have a live version for production and a latest version for testing.
