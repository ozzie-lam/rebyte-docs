# Message

## Insert Message

`POST https://rebyte.ai/api/sdk/threads/{threadId}/messages`

Create a new message in a thread.

**Path parameters**
* thread_id(required): A string with the ID of the thread to create a message for.

**Request body**
* role(required): A string, containing the role of the entity that is creating the message. Currently only user is supported.
* content(required):A string with the content of the message.
* file_ids: A list of File IDs that the message should use. There can be a maximum of 10 files attached to a message. Useful for tools like retrieval and code_interpreter that can access and use files.
* metadata: Set of 16 key-value pairs that can be attached to an object. This can be useful for storing additional information about the object in a structured format. Keys can be a maximum of 64 characters long and values can be a maxium of 512 characters long.


**Example Request**
```shell

curl 'https://rebyte.ai/api/sdk/threads/{thread_id}/messages' \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer $REBYTE_KEY" \
  -d '{
      "role": "user",
      "content": "How does AI work? Explain it in simple terms."
    }'
```

**Return**

A message object.


**Example**
```json
{
    "id": "W_DPv1bwUQ50PC52f44Uo",
    "created_at": 1710415825,
    "thread_id": "p_DFiNmczwUWZjcl47U9X",
    "role": "user",
    "content": "How does AI work? Explain it in simple terms.",
    "metadata": {
        "user": "czy1"
    }
}
```

## List Messages

`GET https://rebyte.ai/api/sdk/threads/{threadId}/messages`

Get list of messages in a thread.

**Path parameters**
* thread_id(required): A string with the ID of the thread to create a message for.

**Query parameters**

* limit: An integer, defaults to 20.A limit on the number of objects to be returned. Limit can range between 1 and 100, and the default is 20.

* order: A string, defaults to desc. Sort order by the created_at timestamp of the objects. asc for ascending order and desc for descending order.

* after: A string, with a cursor for use in pagination. after is an object ID that defines your place in the list. For instance, if you make a list request and receive 100 objects, ending with obj_foo, your subsequent call can include after=obj_foo in order to fetch the next page of the list.

* before: A string, with a cursor for use in pagination. before is an object ID that defines your place in the list. For instance, if you make a list request and receive 100 objects, ending with obj_foo, your subsequent call can include before=obj_foo in order to fetch the previous page of the list.

**Example Request**
```shell
curl 'https://rebyte.ai/api/sdk/threads/{thread_id}/messages'     \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer $REBYTE_KEY" \
```

**Return**

Returns a lit of messages.


**Example**
```json
{
    "list": [
        {
            "id": "W_DPv1bwUQ50PC52f44Uo",
            "created_at": 1710415825,
            "thread_id": "p_DFiNmczwUWZjcl47U9X",
            "role": "user",
            "content": "How does AI work? Explain it in simple terms.",
            "metadata": {
                "user": "czy4"
            }
        }
    ]
}
```

## Get message

`GET https://rebyte.ai/api/sdk/threads/{threadId}/messages/{messageId}`

Get a message by id.

**Path parameters**

* thread_id(required): A string, with the ID of the thread to which this message belongs.

* message_id(required): A string, with the ID of the message to retrieve.

**Example Request**
```shell
curl 'https://rebyte.ai/api/sdk/threads/{thread_id}/messages/{message_id}' \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer $REBYTE_KEY" 
```

**Return**

Returns a message object.

**Example**
```json
{
    "id": "W_DPv1bwUQ50PC52f44Uo",
    "created_at": 1710415825,
    "thread_id": "p_DFiNmczwUWZjcl47U9X",
    "role": "user",
    "content": "How does AI work? Explain it in simple terms.",
    "metadata": {
        "user": "czy4"
    }
}
```

## Update message 

`POST https://rebyte.ai/api/sdk/threads/{threadId}/messages/{messageId}`

Update a message by id.


**Path parameters**

* thread_id(required): A string, with the ID of the thread to which this message belongs.

* message_id(required): A string, with the ID of the message to retrieve.


**Request body**

* metadata: A map. Set of 16 key-value pairs that can be attached to an object. This can be useful for storing additional information about the object in a structured format. Keys can be a maximum of 64 characters long and values can be a maxium of 512 characters long.

**Example Request**
```shell
curl 'https://rebyte.ai/api/sdk/threads/{thread_id}/messages/{message_id}' \
  -H 'Content-Type: application/json' \
  -H "Authorization: Bearer REBYTE_KEY" \
  -d '{
     "role": "user",
      "content": "Updated on 14th March,2024. Happy valentine'\''s day!",
      "metadata":{
        "user":"czy4"
      }
}'
```

**Return**

Returns the modified message object.

**Example**
```json
{
    "id": "W_DPv1bwUQ50PC52f44Uo",
    "created_at": 1710415825,
    "thread_id": "p_DFiNmczwUWZjcl47U9X",
    "role": "user",
    "content": "How does AI work? Explain it in simple terms.",
    "metadata": {
        "user": "czy4"
    }
}
``` 

