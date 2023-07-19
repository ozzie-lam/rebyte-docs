---
description: >-
  This guide covers how to build a chat callable that refines user questions
  with Google Searches to obtain a response from a LLM that references data from
  websites.
---

# Chatbot with Google Search Assistance

## Getting Started

Create a **barebone** callable in the callable builder tab. Make sure to switch the input type to the **ChatDataset**.

***

### Chat Inputs

Chat Callable's input is a message object that contains an array of messages with the fields:

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

***

## Formatting Question for Search Query

Message objects contain the entire conversation history as an array with the last message in the array from the user. In order to send a google search query, we first need to extract the relevant context of the conversation to enhance the user’s question and receive correct search results.

To do this, click the plus and create two code blocks: one to extract the question and the second to extract the conversation history.

<figure><img src="../.gitbook/assets/Screenshot 2023-07-17 at 4.50.44 PM (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2023-07-17 at 4.50.56 PM.png" alt=""><figcaption></figcaption></figure>

Once we extract the question and history with the respected code blocks, we can refine our question with a language model so that it will include the context of the history inside a Model Block.

<figure><img src="../.gitbook/assets/Screenshot 2023-07-17 at 5.09.47 PM.png" alt=""><figcaption></figcaption></figure>

For the model configuration, we want a temperature of 0.1 for a more conservative change and so  that our original question is not altered dramatically.

## Google Search and Summarizing Results

After refining our question, we want to create a google search query using the result from the REFINED\_QUESTION block that will provide links to relevant websites.

<figure><img src="../.gitbook/assets/Screenshot 2023-07-17 at 5.26.07 PM.png" alt=""><figcaption></figcaption></figure>

Our google search query provides us with a few of the most relevant links related to our query. In order to extract the information from these links, we must utilize a Map Reduce block and call a web crawler block on each link to retrieve the details from the google search results.

In order to extract the relevant links and web crawl over them, we want to simplify our GOOGLE\_SEARCH object into a result object with a field for the title and link before starting our Map Reduce block. This can be done with another Code block.

<figure><img src="../.gitbook/assets/Screenshot 2023-07-17 at 5.26.16 PM.png" alt=""><figcaption></figcaption></figure>

Now with a list of relevant links formatted correctly, we can start a Map Reduce loop to collect a summary of each link.

<figure><img src="../.gitbook/assets/Screenshot 2023-07-17 at 5.26.23 PM (2).png" alt=""><figcaption></figcaption></figure>

This loop begins by calling upon a Web Page Crawler Block with each link to retrieve the HTML body of the page.

<figure><img src="../.gitbook/assets/Screenshot 2023-07-17 at 5.26.31 PM.png" alt=""><figcaption></figcaption></figure>

Then, another code block is called upon with the web crawler data to format into content blocks with only the first 2000 bytes of the HTML body.

<figure><img src="../.gitbook/assets/Screenshot 2023-07-17 at 5.26.38 PM.png" alt=""><figcaption></figcaption></figure>

Once the data is collected, a language model block can help us summarize the raw data from the HTML body into a single paragraph for which we can use in our final prompt.

<figure><img src="../.gitbook/assets/Screenshot 2023-07-17 at 5.26.51 PM (1).png" alt=""><figcaption></figcaption></figure>

The last block in the loop is a code block that nicely formats the link summaries into an object for us to reference in our final prompt.

<figure><img src="../.gitbook/assets/Screenshot 2023-07-18 at 1.10.19 PM.png" alt=""><figcaption></figcaption></figure>

## Final Prompt and Returning Result

Lastly, we need to combine the data from all relevant links together along with the original question into a single prompt before sending to our language model. This can be done with a code block that loops through each FORMAT\_SUMMARY object to extract the summary of the links and append it into a single string with the original question.

<figure><img src="../.gitbook/assets/Screenshot 2023-07-18 at 1.12.26 PM.png" alt=""><figcaption></figcaption></figure>

Once this is finished, the last step is to run the final prompt in a language model prompt and extract the results.

<figure><img src="../.gitbook/assets/Screenshot 2023-07-18 at 1.17.55 PM.png" alt=""><figcaption></figcaption></figure>

***

Congratulations, you have created a chatbot that uses google search to find relevant information about the question. Create some test cases and deploy your callable to start using it in any application.
