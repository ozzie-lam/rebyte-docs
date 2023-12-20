# LLM Completion

### Parameters

- Advanced
    - Introduction
        - Supports tera syntax, use {{BlockName}} to reference previous Block output
    - Examples
        - Example Counts
- Prompt
    - Content sent to large language model
    - Supports tera syntax, use {{BlockName}} to reference previous Block output
    - Examples: tera, variables

```xml
Your role is that of a text editor. 
You are expected to peruse the texts provided to you, comprehending them fully, and then distill and summarize them for me. The summary should encapsulate the main theme and essential details of the original text. It should be succinct and expressed in your own words. 
The contents that need to be summarized will be enclosed within three single quotation marks.

The summary should be conducted in accordance with the following regulations:
1. Thematic Statement: Succinctly summarize the main theme or key point of the original text. 
2. Key Details: Enumerate the crucial details or facts from the original text that support the main theme or point. 
3. Overall Conclusion: Distill the conclusion of the original text or the position of the author.

Please organize the summary according to the following structure and reply me:
Introduction: Introduce the main theme or background of the original text.(New line)
Body Paragraph: List and explain the key details and arguments from the original text, summarizing them in your own words. (New line)
Conclusion: Summarize the main points of the original text or present the author's conclusion.(New line)

This is the content that requires summarization:

please reply to me with the phrase: "I apologize for being unable to retrieve content from the URL you provided. Please verify the correctness of the web address"

{{CODE_1.content}}
```


**Config**

- LLM Model Selection
    - Ability to select model provider and specific model
- Temperature
    - The higher the model temperature, the more random the output results. Conversely, the lower the temperature, the more definite the output results.
- Max Tokens
    - The maximum number of tokens generated. Requests can use up to 40,000 tokens, including prompt and model returned content.
    - Different models have different token limits.


**Output**

JSON

| parameter       | type   | description                |
|-----------------|--------|----------------------------|
| prompt.text     | string | the prompt sent to the LLM |
| completion.text | string | the response from LLM      |

**Example**

```json
{ prompt, completion }
    prompt:{ text, tokens, logprobs, top_logprobs }
        text:please reply to me with the phrase: "I apologize for being unable to retrieve content from the URL you provided. Please verify the correctness of the web address"
        tokens:
        logprobs:
        top_logprobs:
    completion:{ text, tokens, logprobs, top_logprobs }
        text:I apologize for being unable to retrieve content from the URL you provided. Please verify the correctness of the web address.
        tokens:
        logprobs:
        top_logprobs:
```
