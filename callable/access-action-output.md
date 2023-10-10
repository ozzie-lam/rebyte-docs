A key part when designing an agent is to reference the output of previous actions. 
Depending on context, the syntax for referencing output may be very different.

## Sample output
- name: `GET_PRODUCTS`
- output: 
```
[
    {"name": "iPhone 12", "price": 1000}, 
    {"name": "iPhone 12 Pro", "price": 1200}
]
```


## Accessing Output in Javascript Context
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
This is done by using the dot (.) like \{{ product.name \}}. Specific members of an array or tuple are accessed by using the .i notation, where i is a zero-based index. In dot notation variable can not be used after the dot (.).

```
{{GET_PRODUCTS.0.name}}
```

Here are the full list of places where you can use the `{{ }}` syntax:
* Prompt field in LLM action
* URL field in HTTP action
