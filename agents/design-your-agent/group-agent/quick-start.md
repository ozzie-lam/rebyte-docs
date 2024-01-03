# Quick Start

In this tutorial, we will show you how to create a group agent that will discuss a topic between two agent.

## Step 1: Create A Group Agent

* Navigate to the "Agents" tab in the sidebar and then click on "Create Agent" on the top right.

* Choose the "Group Agent" option.

* Fill in the name,description, and set the visibility of your group agent.

<figure><img src="../../../images/group-1.png"></figure>


## Step 2: Design Your Group Agent

* This agent only has four actions:`Input`, `Thread`, `Agent Group` and `Output`, and you can't add or delete any action.

* The `Input` and `Output` actions are the same as a stack agent.You can create your own datasets to test your agent.

**Thread**

<figure><img src="../../../images/group-2.png"></figure>

* Configure the "Max Number of Previous Runs on Thread" in the `Thread` action using the toggle button. This is the maximum number of history messages that the agent will record and send to the model everytime it runs.

* The longer the history, the more context the model will have to work with. However, the longer the history, the slower the agent will run. 
  
**Agent Group**

<figure><img src="../../../images/group-3.png"></figure>

* Choose the agents you want to use in the `Agent Group` action. Here we choose the two student chatbot agents we created.

* NOTE: You must be familiar with the agent's function and the agent's input and output format. Also make sure the agent's output format is compatible with the next agent's input format.
  
* Specify the execution order of the agents in the group agent. The agent will run the agents in the order you specified. For example, here we put "round robin" in Agent Selector Instruction, so the agent will run the agents one by one in a loop.

* You can also set the maximum rounds of conversation between agents. If the conversation between agents exceeds the maximum rounds, the agent will stop running.

And that's it!

## Step 3: Test Your Group Agent

* This is basically the same a [testing a stack agent](../../test-your-agent/overview.md). 
  
* The only difference is that rather than focusing on the output of only one agent, you should take a good look at the output of all the agents in the group agent and try to find out if their behavior is what you want.



