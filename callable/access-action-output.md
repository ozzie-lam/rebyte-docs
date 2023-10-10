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

## Accessing Output in Prompt Template
This is done by using the dot (.) like \{{ product.name \}}. Specific members of an array or tuple are accessed by using the .i notation, where i is a zero-based index. In dot notation variable can not be used after the dot (.).

```
{{GET_PRODUCTS.0.name}}
```