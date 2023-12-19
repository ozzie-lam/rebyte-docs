# Bilibili subtitle agent

Help you get bilibili subtitles and summarize the content.


### Setup the testing data in `Datasets`

```json
[
  {
    "role": "user",
    "content": "BV1Lu411J7Z8"
  }
]
```


### Extract content from `Code Action`

```js
_fun = (env) => {
  // use `env.state.Action_NAME` to refer output from previous Actions.
  return env.state.INPUT.messages.slice(-1)[0].content
} 
```

### Use LLM to process user's input

```javascript
_fun = (env) => {
  // use `env.state.Action_NAME` to refer output from previous Actions.
 return env.state.GET_BV.completion.text
}
```

### Extract content from `Code Action`

```javascript
_fun = (env) => {
  // use `env.state.Action_NAME` to refer output from previous Actions.
 return env.state.GET_BV.completion.text
}
```

### Use `Http Request Maker` and request for CID

```javascript
api.bilibili.com/x/player/pagelist?bvid={{BV}}
```

### Extract content from `Code Action`

```javascript
_fun = (env) => {
  // use `env.state.Action_NAME` to refer output from previous Actions.
 return env.state.GET_CID.body.data[0].cid
}
```

### Use `Http Request Maker` and request for the url for subtitles

```javascript
api.bilibili.com/x/player/v2?bvid={{BV}}&cid={{CID}}
```

### Extract content from `Code Action`

```javascript
_fun = (env) => {
  // use `env.state.Action_NAME` to refer output from previous Actions.
  // const data = JSON.stringify(env.state.GET_URL.body)
  // const regex = /<subtitle>(.*?)<\/subtitle>/;
  // const match = data.match(regex);
  // const subtitleURL = match ? match[1] : "";
  // const obj = subtitleURL.replace(new RegExp("\\\\\"","gm"),"\"")
  // const result = JSON.parse(obj)['subtitles'][0]['subtitle_url'].replace("//", "")
  const url = env.state.GET_URL.body.data.subtitle.subtitles[0].subtitle_url
  const result = url.replace(/\/\//g, "");
  return result
  
}
```

### Use `Http Request Maker` and request for the subtitles

```javascript
{{GET_CC_URL}}
```

### Extract content from `Code Action`

```javascript
_fun = (env) => {
  // use `env.state.Action_NAME` to refer output from previous Actions.
  let arr = []
  for(let i in env.state.GET_CC.body.body) {
    arr.push(env.state.GET_CC.body.body[i].content)
  }
 return arr.join(',')
}
```

### Send subtitles to the LLM to summarize
```json
{% if GET_URL.body.data.subtitle.subtitles[0].subtitle_url == "" %}
please reply to me with the phrase: "I apologize for being unable to retrieve content from the URL you provided. Please verify the correctness of the web address"

{% else %}
You are an AI with advanced comprehension and summarization skills. Your task is to read the following passage and provide a concise, clear summary that captures the main points and key details. 

Passage: 
{{CC}}

Please provide a summary of the above passage and respond to me in Chinese.

{% endif %}
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