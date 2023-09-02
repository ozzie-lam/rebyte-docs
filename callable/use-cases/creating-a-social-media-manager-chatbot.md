# Creating a Social Media Manager Chatbot

## Overview

Let's imagine that we are responsible for managing the social media presence of an up and coming startup and would like the help of a language model to help write twitter posts. We want to create a chat bot that can answer questions as if it has the knowledge of an expert social media manager.

ReByte makes the process of building a personalized chat bot fast and simple. Let's look at how this can be done with the power of Callable and Copilot.

## Getting Started

Navigate to the **Callable Builder** tab in the top right of the navigation bar and go ahead and press **Create Callable**. Name your callable **"social-media-call"** and give the following description:

> callable to support creating social media posts

Select **Private** and choose the **Barebone** template callable before pressing **Create**.

Once inside the Callable Builder, you should see two blocks: INPUT, OUTPUT. Since we are creating a Chatbot let's switch the **input type** in the **INPUT** block to **ChatDataset**.

<details>

<summary>Understanding Chat Inputs</summary>

## Chat Inputs

Chat Callable's input is a message object that contains an array of messages.

#### Message Object

The `Message` object is a high-level entity that holds an array of individual message items.

* `messages`: An array of message items. Each item in the array is an object that consists of two properties: 'role' and 'content'.

#### Message Item

Each message item is an individual message with its associated role.

* `'role'` Role related to the message (e.g., 'user', 'assistant').
* `'content'` Text of the message.

### Example

Here is an example of what a `Message` object might look like:

```javascript
{
  "messages": [
    {
      "role": "user",
      "content": "Hello, how can I help you?"
    },
    {
      "role": "assistant",
      "content": "I'm here to assist you. What do you need?"
    },
    {
      "role": "user",
      "content": "I need information on your new products."
    }
  ]
}
  
```

</details>

<details>

<summary>Understanding Callable Blocks</summary>

Blocks are fundamental units that form logical sequences inside a Callable. They operate similarly to server-less functions, running independently yet capable of working in cohesion to create complex features.

Think of each block as an individual piece in a larger puzzle that is your Callable. Every block has its unique role and introduces a new functionality to the Callable. This could be anything from making curl requests, leveraging large language models, extracting specific data, to retrieving knowledge.

A key attribute of these blocks is that they can interact with one another by calling upon each other's results. This ability to collaborate makes them incredibly versatile and adaptable, allowing you to build intricate and sophisticated features by chaining them together in the Callables.

</details>

***

## Callable Code and Model Blocks

For this application, we want to create a callable that takes in chat inputs and outputs a response from a language model in the form of a message item (See [#understanding-chat-inputs](creating-a-social-media-manager-chatbot.md#understanding-chat-inputs "mention")).

We want to start by creating two referable code blocks that return:

1. The question asked by the user
2. The history of the chat

Both of these can be sourced from parsing the input message object with the following blocks.

### EXTRACT\_QUESTION Block

This Code block returns the content of the last element in the message array

<figure><img src="../../.gitbook/assets/Screenshot 2023-07-24 at 5.21.32 PM.png" alt=""><figcaption></figcaption></figure>

### HISTORY Block

This Code block joins the content of every message in the array except the last message and returns it in a string.

<figure><img src="../../.gitbook/assets/Screenshot 2023-07-24 at 5.21.39 PM.png" alt=""><figcaption></figcaption></figure>

Once we have parsed the History and Question from the input, we can references these inside a well designed prompt and send everything to ChatGPT. This can be done inside a Model Block.

### OUTPUT\_STREAM Block

This Model block uses the return of the History block and the Extract Question block and wraps it into prompt that will help specify what kind of answer we want from ChatGPT.

{% hint style="info" %}
Notice that when referencing block variables inside the Model Block prompt section, we must use the syntax`{{BLOCK_NAME}}`.
{% endhint %}

<figure><img src="../../.gitbook/assets/Screenshot 2023-07-24 at 5.21.45 PM.png" alt=""><figcaption></figcaption></figure>

Lastly, we want to return the answer ChatGPT gives into a message item object. This can be done with a Code block again.

### GET\_ANSWER Block

This Code block returns a message item object that contains content from the output of the OUTPUT\_STREAM Block.

<figure><img src="../../.gitbook/assets/Screenshot 2023-07-24 at 6.09.29 PM (1).png" alt=""><figcaption></figcaption></figure>

## Test and Deploy

Once you finish creating the necessary blocks for your callable. Go ahead and press **Run TestCases**. If there are no errors, you can deploy your callable by pressing **Deploy**.

## Creating Copilot

After successfully deploying your callable, you can quickly turn your callable into a usable Chat Copilot. Navigate to **My Copilots** and click on **Create Copilot**. Name your Copilot **"Social Media Manager"** and enter the description

> An expert social media content manager to generate tweets and posts for your brand!

Select **Private** and choose **Chat**. Then press **Select Callable** and select **social-media-call**. Select **latest** for the version.

Under **Example Prompts**, paste the following prompts:

1. Write a tweet to launch my new crypto startup: Kr1ptu@
2. Write an Instagram post to announce that my sunglasses brand is now shipping to Europe
3. Write a Facebook post to say I'm offering 30% discount on my online coding courses

Finally, click **Create Copilot.**

## Try it out!

Go ahead and use your new chat copilot and see what tweets you can make!
