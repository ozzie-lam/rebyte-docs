# Call agent

We provide `Call Agent` action so that you can call other agents in your agent as an action.

## Usage

* Add a `Call Agent` action to your agent. 

<figure><img src="../../../../images/call-agent-1.png"></figure>

* Choose the agent you want to call(let's call it **"Agent B"**) and select the right version.

<figure><img src="../../../../images/call-agent-2.png"></figure>

<figure><img src="../../../../images/call-agent-3.png"></figure>

* Fill in the "Input Args" of Agent B; And the output of Agent B is the output of this action.

<figure><img src="../../../../images/call-agent-4.png"></figure>

* **NOTE**: Make sure you fully understand the input format of Agent B before filling in the "Input Args". Otherwise, the system will throw an error. 

* Use the "Block Configs" to configure Agent B's action.

## Output

The output of this action is as follows:

<figure><img src="../../../../images/call-agent-5.png"></figure>

JSON

| parameter  | type   | description                                |
|------------|--------|--------------------------------------------|
| status.run | object | the result of the calling(success or fail) |
| results    | object | the response                               |
| others     | object | the status of the agent being called       |