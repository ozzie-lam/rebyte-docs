# Making Curl Requests

## Callables

After deploying a Callable, Cortex provides the direct curl request to send inputs to.

```sh
curl -L https://trycortex.ai/api/sdk/p/[pID]/a/[aID]/r \
    -H "Authorization: Bearer $CORTEX_API_KEY" \
    -H "Content-Type: application/json" \
    -d '{
      "version": 1,
      "config": {
        "OUTPUT_STREAM":{
          "provider_id":"openai",
          "model_id":"gpt-3.5-turbo-16k",
          "use_cache":true,
          "use_semantic_cache":false},
        "RETRIEVALS":{
            "knowledge":[{
              "project_id":"$pID",
              "data_source_id":"$DATASOURCE"}],
            "top_k":10,
            "filter":{"tags":null,"timestamp":null},
            "use_cache":false}},
      "blocking": true,
      "inputs": [{ "Key": "Value" }]
    }'
```

By providing a specified key and value pairs into the input, the HTTP response will contain a json with the corresponding output from the callable.

### Request body



| Name                 | Description                                                                   |
| -------------------- | ----------------------------------------------------------------------------- |
| `version (Required)` | (`integer \| 'latest'`) specify which version of the callable you want to run |
| `config (Required)`  | (`object`) configures the callable blocks                                     |
| `inputs (Required)`  | (`array`) array of key and value pairs that will be sent to the callable      |



## Documents

Example curl request

```bash
curl -L https://trycortex.ai/api/sdk/p/[pID]/knowledge/[knowledgeName]/d/[docID] \
    -H "Authorization: Bearer $CORTEX_API_KEY" \
    -H "Content-Type: application/json" \
    -d '{
      “text”: “value”
    }'
```

### Request body

* text (string)
  * the document text
