# Agent API

The Agent API allows you to build AI agent within your own applications. It provides a set of APIs to interact with the agent, such as sending messages, uploading files, and creating threads.

## Overview

A typical integration of the Agent API has the following flow:

1. Create an Agent on rebyte Agent editor by defining its custom actions, such as `Model`, `Data`, `Tools`, `Control Flow`, etc. Pick the model and parameters that you want to use.

2. Create a Thread when a user starts a conversation.

3. Add Messages to the Thread as the user asks questions.

4. Run the Agent on the Thread to generate a response.
