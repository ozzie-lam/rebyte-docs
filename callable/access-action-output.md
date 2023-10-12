A key part when designing an agent is to reference the output of previous actions. 
Depending on context, the syntax for referencing output may be slightly different.

## Sample output
let's say we have an action with the following output:
- action name: `GET_PRODUCTS`
- output: 
```
[
    {"name": "iPhone 12", "price": 1000}, 
    {"name": "iPhone 12 Pro", "price": 1200}
]
```


## Accessing GET_PRODUCTS in Javascript Context
There is a special variable called `env.state` that can be used to access the output of previous actions. The output variable is a dictionary, the key is the name of the action name, and the value is the output of the action. For example, if you have an action called `GET_PRODUCTS`, then you can access the output of this action by using 

```
env.state['GET_PRODUCTS'].0.name
```
or 

```
env.state.GET_PRODUCTS.0.name
```

Here are the full list of places where you can use the `env.state` variable:
* Javascript code action
* Condition field in Loop action
* Header field in HTTP action
* Body field in HTTP action
* Message field in LLM action
* Function field in LLM action

## Accessing Output in Non-Javascript Code

```
{{GET_PRODUCTS.0.name}}
```
* Dot notation is used to access the output of previous actions
* For array, you can use `0` to access the first element, `1` to access the second element, and so on
* For complex control, see [Rebyte Template Language](/callable/prompt-template-language.md)

Here are the full list of places where you can use the `{{ }}` syntax:
* Prompt/Instruction field in LLM action
* URL field in HTTP action
* URL field in Web Crawler action
* File UUID field in File loader action
* Query field in Knowledge action
* Query field in Google Search action
