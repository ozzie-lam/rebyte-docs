# Default action

##Input

The input for the entire program flow, cannot be modified. 
 
###Parameters

- Input type
    - Select from predefined Datasets
    - When connecting to Chat, the latest 10 history dialogues will be sent to the Agent as input information by default, formatted as follows
    ```json
    {
    "Messages":[
    {
        "role": "user",
        "content": "The content."
    },
    {
        "role": "assistant",
        "content": "The content."
    }
    ]
    }
    ```
    - output
        - Output the correct data
    