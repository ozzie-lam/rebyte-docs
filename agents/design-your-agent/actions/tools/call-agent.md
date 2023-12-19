# Call agent

### Description

You can call another Agent. 

### Parameters

- AgentId
	- The AgentId of the Agent being called.
- projectId
	- The projectId where the called Agent is located.
- apiKey
	- The apiKey used to access the corresponding Agent.
- version
	- The version number of the agent that's being called; The default setting is the lastest version.
- inputArgs
	- The input arguments corresponding to inputs, refer to the [API](); the parameters passed here must be a string.
- blocking
	- Just fill in true. 

### Output

JSON

| parameter  | type   | description                                |
|------------|--------|--------------------------------------------|
| status.run | object | the result of the calling(success or fail) |
| results    | object | the response                               |
| others     | object | the status of the agent being called       |