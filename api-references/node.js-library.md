# Node.js Library

## Documents

#### <mark style="color:purple;">.getDocument(knowledgeName: string, documentID: string)</mark>

The function `.getDocument` takes in two parameters: `knowledgeName` and `documentID`. It retrieves a specific document from a specified knowledge base. The function returns an `AxiosPromise` with the document object.

Example return json:

<pre class="language-javascript"><code class="lang-javascript">{
<strong>    "document": {
</strong>        "created": integer,
        "document_id": string,
        "timestamp": integer,
        "tags": string[],
        "source_url": string,
        "hash": string,
        "text_size": integer,
        "chunk_count": integer,
        "chunks": [],
        "text": string
    } 
}
</code></pre>



#### <mark style="color:purple;">.uploadDocument(knowledgeName: string, documentID: string, document: createDocument)</mark>

The function `.uploadDocument` takes in three parameters: `knowledgeName`, `documentID`, and `document`. It uploads a new document to a specified knowledge base. The function returns an `AxiosPromise` with the newly uploaded document object and the knowledge object that the document was uploaded to.

The Document object has the following interface:

```javascript
interface createDocument {
  timestamp?: number;
  tags?: string[];
  text?: string | null;
  source_url?: string | null;
};
```

Example return json:

```javascript
{
    "document": {
        "created": integer,
        "document_id": string,
        "timestamp": integer,
        "tags": [],
        "source_url": string,
        "hash": string,
        "text_size": integer,
        "chunk_count": integer,
        "chunks": [
            {
                "text": string,
                "hash": string,
                "offset": 0,
                "vector": [],
                "score": null
            }
        ]
    },
    "knowledge": {
        "name": string,
        "description": string,
        "visibility": "private" | "public",
        "config": "{\"provider_id\":\"openai\",\"model_id\":\"text-embedding-ada-002\",\"extras\":null,\"splitter_id\":\"base_v0\",\"max_chunk_size\":365,\"use_cache\":false}",
        "runnerProjectId": string,
        "lastUpdatedAt": string,
        "hub": null
    }
}
```



#### <mark style="color:purple;">.deleteDocument(knowledgeName: string, documentID: string)</mark>

The function `.deleteDocument` takes in two parameters: `knowledgeName` and `documentID`. It deletes a specific document from a specified knowledge base. The function returns an `AxiosPromise` with the deleted document object.



## Callable



#### <mark style="color:purple;">`.runCallable(callableID: string, data: CallableParams): AxiosPromise<{run: RunType}>`</mark>

This function runs a callable identified by `callableID` with the given `data`. The `data` parameter must be an object of type `CallableParams` which includes the `version`, `config`, `inputs`, `blocking`, and `block_filter` properties. The `version` property specifies the version of the callable to run. The `config` property is an object of configuration parameters for the callable. The `inputs` property is an array of input values for the callable. The `blocking` property is a boolean that specifies whether the function should wait for the callable to complete before returning. The `block_filter` property is an array of block status filters for the callable. The function returns a promise that resolves to an object of type `AxiosPromise<{run: RunType}>` which includes the status of the run.



#### <mark style="color:purple;">`.runCallableWithStream(callableID: string, data: CallableParams): AxiosPromise`</mark>

This function runs a callable identified by `callableID` with the given `data` and streams the output. The `data` parameter must be an object of type `CallableParams` which includes the `version`, `config`, `inputs`, `blocking`, and `block_filter` properties. The `version` property specifies the version of the callable to run. The `config` property is an object of configuration parameters for the callable. The `inputs` property is an array of input values for the callable. The `blocking` property is a boolean that specifies whether the function should wait for the callable to complete before returning. The `block_filter` property is an array of block status filters for the callable. The function returns a promise that resolves to an object of type `AxiosPromise` which includes the streamed output of the callable.



#### <mark style="color:purple;">`.runChatCompletion(version: string, messages: Message[], input: string, projectID:string, knowledgeName: string, copilotID: string)`</mark>

| Name            | Description                                                                     |
| --------------- | ------------------------------------------------------------------------------- |
| `version`       | (`string`) `"latest"` \| version number                                         |
| `messages`      | (`Message[]`) array of messages previously sent to the chat callable            |
| `input`         | (`string`) chat message that wants to be answered                               |
| `projectID`     | (`string`) projectID of user who created the knowledge that is being referenced |
| `knowledgeName` | (`string`) name of knowledge being referenced                                   |
| `copilotID`     | (`string`) ID of chat copilot                                                   |
