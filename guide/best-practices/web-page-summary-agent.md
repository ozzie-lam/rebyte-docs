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
    "content": "Introduce this web page: https://towardsdatascience.com/an-introduction-to-openai-function-calling-e47e7cd7680e"
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