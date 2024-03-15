# Thread

## Create thread

`POST https://rebyte.ai/api/sdk/threads`

Create a new thread.

**Request body**
* messages: An array of messages to start the thread with.
* metadata: Set of 16 key-value pairs that can be attached to an object. This can be useful for storing additional information about the object in a structured format. Keys can be a maximum of 64 characters long and values can be a maxium of 512 characters long.

**Example Request**

```shell
curl 'https://rebyte.ai/api/sdk/threads' \
--H 'Content-Type: application/json' \
--H 'Authorization: Bearer $REBYTE_KEY' \
--H 'Cookie: NEXT_LOCALE=en' \
--data '{
     "metadata": {
        "user": "abc123"
      }
}'
```

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

**Query parameters**
* limit: An integer, with the maximum number of threads to return. Default is 20.
* order: A string, with the order to return the threads. Default is desc.
* before: A string, used as a cursor for use in pagination. after is an object ID that defines your place in the list.
* after: A string, used as a cursor for use in pagination. before is an object ID that defines your place in the list.



**Example Request**
```shell
curl  'https://rebyte.ai/api/sdk/threads?limit=10&order=desc' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer $REBYTE_KEY' \
-H 'Cookie: NEXT_LOCALE=en'
```

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

**Example Request**
```shell
curl 'https://rebyte.ai/api/sdk/threads/{thread_id}' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer $REBYTE_KEY' \
-H 'Cookie: NEXT_LOCALE=en'
```

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

**Example Request**
```shell
curl 'https://rebyte.ai/api/sdk/threads/{thread_id}' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer $REBYTE_KEY' \
-H 'Cookie: NEXT_LOCALE=en' \
--data ' {
    "metadata": 
    {
        "modified": "true",
        "user": "czy"
    }
 }'
```

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