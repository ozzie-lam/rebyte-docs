# Text Completion

**Parameters**

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
{% if CODE_1.content != "" and REFINE_RESULT.language == 'zh' %}
你的角色是文字编辑
你应该阅读我提供给你的文字，充分理解后将其提炼总结告诉我

总结应该概括原文的主旨和重要细节。总结应该是简洁明了的，以自己的话语表达。以下是总结应包含的内容：
a. 主题陈述：简要概括原文的主题或主要观点。
b. 关键细节：列举原文中支持主题或观点的关键细节或事实。
c. 总体结论：提炼出原文的结论或作者的立场。

总结请按照以下结构进行组织后回复我：
引言：引入原文的主题或背景。 (换行)
主体段落：列举并解释原文中的关键细节和论据，用自己的话语进行概括。(换行)
结论：总结原文的主要观点或提出作者的结论。(换行)

以下是需要总结的文本内容：

{% elif CODE_1.content != "" %}
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

{% elif REFINE_RESULT.language == 'zh'%}
请您用以下短语回复我：“对不起，无法从您提供的网址中检索内容。请确认网址的正确性。”

{% else %}
please reply to me with the phrase: "I apologize for being unable to retrieve content from the URL you provided. Please verify the correctness of the web address"

{% endif %}

{{CODE_1.content}}
```
<!-- | Parameter | Description                              |
|---|------------------------------------------|
| prompt | The prompt to be sent to the model       | -->

**Config**

- LLM Model Selection
    - Ability to select model provider and specific model
- Temperature
    - The higher the model temperature, the more random the output results. Conversely, the lower the temperature, the more definite the output results.
- Max Tokens
    - The maximum number of tokens generated. Requests can use up to 40,000 tokens, including prompt and model returned content.
    - Different models have different token limits.


<!-- | Parameter | Description                              |
|---|------------------------------------------|
| max_tokens | The maximum number of tokens to generate |
| temperature | What sampling temperature to use         | -->

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
