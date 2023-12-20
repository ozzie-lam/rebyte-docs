# Search engine agent

Summarize web page contents for you.

### Setup the testing data in `Datasets`

```json
[
  {
    "role": "user",
    "content": "Who won the last UEFA Champions League?"
  },
  {
    "role": "assitant",
    "content": "The last winner of the UEFA Champions League was Manchester City in the 2022-23 season. This was their first title in the competition. Real Madrid holds the record for the most victories in the Champions League, having won it 14 times [0][1]."
  },
  {
    "role": "user",
    "content": "Who scored the winning goal?"
  }
]
```


### Use `Code Action` to get the last message

```javascript
_fun = (env) => {
  // use `env.state.Action_NAME` to refer output from previous Actions.
  return env.state.INPUT.messages.slice(-1)[0].content
}
```

### Use `Code Action` to get the chat history

```javascript
_fun = (env) => {
  // use `env.state.Action_NAME` to refer output from previous Actions.
 return env.state.INPUT.messages.slice(0, env.state.INPUT.messages.length - 1).map((m) => m.content).join("\n")
}
```

### Use `Code Action` to extract content

```txt
{# Your prompt here, for example: 'Answer those question based on the following content.' #}
{# Begin your prompt below: #}
This is the question: {{EXTRACT_QUESTION}}
This is the conversation history: {{HISTORY}}

Add necessary contexts to the question with the help of conversation history. If the contexts are irrelevant don't change the question. Give the question here:
```

### Use `Google_search` to search for related contents
```javascript
{{REFINED_QUESTION.completion.text}}
```

### Use `Code Action` to extract content

```javascript
// Extracts title, snipet and link from the google search's organic results.
// capped at 3
_fun = (env) => {
  if (!env.state.GOOGLE_SEARCH.organic_results) {
    return [
      {
        title: "",
        link: ""
      }
    ]
  }

  return env.state.GOOGLE_SEARCH.organic_results.map((r) => {
    return { title: r.title, link: r.link, snippet: r.snippet };
  }).slice(0, 3);
}
```

### Map the results for parallel processing

```javascript
SEARCH_EXTRACT
```

### Use `WEB_CRAWL` to scan the page 
```javascript
{{SEARCH_RESULT_LOOP.link}}
```

### Use `Code Action` to extract content
```javascript
// for each link, crawl its content and capped at 2000 bytes
_fun = (env) => {
  return {
    content: env.state.WEB_CRAWL_1.data ? env.state.WEB_CRAWL_1.data[0].results[0].text.slice(0, 2000) : "",
  };
} 
```

### Use LLM to analyze the contents
```json
{# Your prompt here, for example: 'Answer those question based on the following content.' #}
{# Begin your prompt below: #}

Given the following question:
"""
{{EXTRACT_QUESTION}}
"""

Extract the text from the following content relevant to the question and summarize it:
"""
{# {{GOOGLE_REFERENCES.content}} #}
{{SEARCH_RESULT_LOOP.snippet}}
"""

Extracted summarized content:
"""
```

### Use `Code Action`` to extract content
```javascript
_fun = (env) => {
  return {
    summary: env.state.MODEL_SUMMARIZE.completion.text.trim(),
    link: env.state.SEARCH_RESULT_LOOP.link
  };    
}
```

Use `Code Action` to extract content and make prompt
```javascript
const _example = (example) => {
  // prompt = `QUESTION: ${example.question}\n`;
  let prompt = "CONTENT:\n";
  prompt += '"""\n';
  example.forEach((d, i) => {
    if (i > 0) {
      prompt += '\n';
    }
    prompt += `link [${i}]: ${d.link}\n`;
    prompt += `content: ${d.summary.replaceAll('\n', ' ')}\n`;
  });
  prompt += '"""\n';
  console.log(prompt)
  return prompt;
}

_fun = (env) => {
  prompt = 'Given the following questions, reference links and associated content, create a final answer with references. If some of answer can be formatted in table format, format in table format. Answer should be accurate and concise. \n\n Never tell me "As a language model ..." or "As an artificial intelligence...", I already know you are a LLM. Just tell me the answer. \n\n';
  // env.state.EXAMPLES.forEach((e) => {
  // prompt += _example(e);
  // prompt += `FINAL:\n"""\n${e.final}\n"""\n`;
  // prompt += "\n";
  // });
  prompt += "QUESTION:" + env.state.EXTRACT_QUESTION + "\n";
  prompt += _example(env.state.FORMAT_SUMMARY);

  prompt += `FINAL:\n"""\n`;

  return { prompt }
}
```

### Send the prompt to LLM
```json
{{FINAL_PROMPT.prompt}}
```
### Extract `OUTPUT_STREAM` as output
```json
{{FINAL_PROMPT.prompt}}
```

