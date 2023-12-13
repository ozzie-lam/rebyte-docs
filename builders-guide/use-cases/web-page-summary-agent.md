# Web page summary agent

Summarize web page contents for you.

### Setup the testing data in `Datasets`

```json
[
 {
    "role": "user",
    "content": "https://book.douban.com/subject/30360449/"
  }
]
[
  {
    "role": "user",
    "content": "介绍一下这个链接 https://towardsdatascience.com/an-introduction-to-openai-function-calling-e47e7cd7680e"
  }
]
```


### Extract content from `Code Action`

```javascript
_fun = (env) => {
  // use `env.state.Action_NAME` to refer output from previous Actions.
  return env.state.INPUT.messages.slice(-1)[0].content
}
```

### Use LLM to process user's input

```javascript
You're a link extractor, which extracts http or https links from given text, output the result as a json format, output contains two fields, first is link, which contains the link extracted from text, second is language, which contains language code of given question.
Here's the given text, let's begin:
{{EXTRACT_QUESTION}}
```

### Extract content from `Code Action`

```javascript
_fun = (env) => {
  // use `env.state.Action_NAME` to refer output from previous Actions.
  const output = JSON.parse(env.state.REFINE.completion.text)
  // if link exists, output link
  // if links exists, output the first element
  return {
    link: output.link ? output.link : (output.links ? output.links[0] : ""),
    language: output.language ?? 'en'
  }
}
```

### Use `WEB_CRAWL Action` to collect information


### Extract content from `Code Action`

```javascript
_fun = (env) => {
  let content = env.state.WEB_CRAWL_1.data ? env.state.WEB_CRAWL_1.data[0].results[0].text.slice(0, 3000) : "";
  content = content.replace(/\n/g, ""); // 去除换行符
  return {
    content: content,
  };
}
```

### Send the web page content to the LLM
```javascript
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

### Extract content from `Code Action`

```javascript
_fun = (env) => {
  // use `env.state.Action_NAME` to refer output from previous Actions.
 return {
   role: "assistant",
   content: env.state.OUTPUT_STREAM.completion.text,
   retrievals: env.state.RETRIEVALS
 }
}
```

### Output the final results