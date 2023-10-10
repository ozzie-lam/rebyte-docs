# Agent Execution Runtime

## Execution Model
Agent is a sequential list of actions, each action is executed in strict order which means the previous action must be completed before the next action can be executed. Action can access output of **all actions** that are executed before it, and the output of the last action is the output of the agent. The input of the first action defines the input shape of the agent.
Agent execution is purely stateless, which means each execution is independent of each other. 

## Execution Traces
Each agent execution is recorded as a trace, which contains the following information:
- **Trace ID**: The ID of the trace, can be used to query the trace.
- **Status**: success, failed, running
- **Run type**: 'prod' when the agent is executed via API, 'design' when the agent is executed via agent builder.
- **Detail**: rebyte will record the detail of each action execution, including the input, output, and error message if any.