# Action Extension

## What is an Action Extension?
Action Extension is a way to extend rebyte agent with your own code. We provide a list of pre-built Action extension for common use cases, a typical extension is to invoke another agent inside current agent, and do some data transformation before/after the agent is called. For example, you might have an agent **X** for handing user's air ticket booking request, and you want to invoke this agent **X** inside another agent, let's say trip planning agent **Y**. In this scenario, you can use in-house pre-built Action Extension **Call Agent** to invoke agent **X** inside agent **Y**.

## Pre-built Action Extension

* **Call Agent**: Invoke another agent inside current agent, and do some data transformation before/after the agent is called.
* **Data Visualization**: Visualize data in a table or chart.
* **Stable Diffusion**: generate a stable diffusion of a given text.
* **DALL-E**: generate an image from a given text.
* more to come...

## Rebyte CLI

Rebyte CLI is a command line tool for building and deploying action extension.
Check the instruction at [ReByte CLI](https://github.com/ReByteAI/rebyte-cli)

