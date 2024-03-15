# Thread

## Create thread

`POST https://rebyte.ai/api/sdk/threads`

Create a new thread.

**Request body**
* messages: An array of messages to start the thread with.
* metadata: Set of 16 key-value pairs that can be attached to an object. This can be useful for storing additional information about the object in a structured format. Keys can be a maximum of 64 characters long and values can be a maxium of 512 characters long.

**Return**

A thread object.

**Example**
```json
{
    "id": "2hWVPNfrHv1IiVN7ia-4P",
    "created_at": 1710481773,
    "metadata": {
        "user": "abc123"
    }
}
```


### List threads

`GET https://rebyte.ai/api/sdk/threads`

Get list of threads.

**Return**

A list of thread objects.


**Example**
```json
{
    "list": [
        {
            "id": "2hWVPNfrHv1IiVN7ia-4P",
            "created_at": 1710481773,
            "metadata": {
                "user": "abc123"
            }
        },
        {
            "id": "NGXTNrg-34seXYc-PCVFu",
            "created_at": 1710415453,
            "metadata": {
                "user": "abc123"
            }
        },
        {
            "id": "MRlX-SOAo5gAx1mxBe7S4",
            "created_at": 1710407916
        }
    ]
}
```
### **Get thread**

`GET https://rebyte.ai/api/sdk/threads/{thread_id}`

Get a thread by id.

**Path parameters**
* thread_id(required): A string, with the ID of the thread to retrieve.

**Returns**
The thread object matching the specified ID.

**Example**
```json
{
    "id": "cB1-_3wh5ZWtUPJU4xIuU",
    "created_at": 1710415223,
    "metadata": {
        "user": "czy",
        "modified": "true"
    }
}
```

### **Update thread**

`POST https://rebyte.ai/api/sdk/threads/{thread_id}`

Update a thread.

**Path parameters**
* thread_id(required): A string, with the ID of the thread to retrieve.

**Request body**
* metadata: Set of 16 key-value pairs that can be attached to an object. This can be useful for storing additional information about the object in a structured format. Keys can be a maximum of 64 characters long and values can be a maxium of 512 characters long.

**Returns**
The modified thread object matching the specified ID.

**Example**
```json
{
    "id": "cB1-_3wh5ZWtUPJU4xIuU",
    "created_at": 1710415223,
    "metadata": {
        "modified": "true",
        "user": "czy"
    }
}
```