# Knowledge Search

Search action allow Agents to make queries to specified knowledge base. This is useful for retrieving information from a knowledge base , later those retrieved information can be used as context for further generation. 
Retrieval Augmented Generation (RAG) agent is a good example of this use case.

Search Action consist of the following fields:

* **Query:** Provide the desired prompt to look for inside your knowledges
* **Knowledge:** Knowledge that you want to search in. You can select multiple knowledge bases. Technically, each knowledge in rebyte can be unique identifier by its knowledge name and project who owns it. 
* **Include Tags:** Add tags that you want to include in your search. Notes tags are exact match which means if you add "tag1" it will only include documents that have "tag1"
* **Exclude Tags:** Add tags that you want to exclude in your search. Notes tags are exact match which means if you add "tag1" it will exclude all documents that have "tag1"
* **Max Documents:** Maximum number of chunks to return. Chunk size is determined when knowledge is created.

## Example

### Spec
| Parameter | Description                       |
|-----------|-----------------------------------|
| query     | query for searching the knowledge |

### Config

| Parameter           | Description                    |
|---------------------|--------------------------------|
| knowledge to search | list of knowledge to search in |
| number_of_results   |  |
| include tags        |  |
| exclude tags        |  |



