# Knowledge

In ReByte, we provide knowledge base capability, enabling agents to interact with your private data. Users can store and manage their personal data in the knowledge. 

Many data sources are supported, including: local files, notion, github, discord, etc.

## How Knowledge Works?

### Document

Each knowledge contains a list of documents, each document is identified by a unique document id within the knowledge.

### Chunk

Document will be chunked into many chunks, each chunk identified by a unique chunk id within the document. Chunks will be sent to LLM embedding service to get the embedding vector.
When creating knowledge, user can specify the chunk size, which will determine how many chunks a document will have. Typically, chunk size range from a hundred to a few thousand tokens.
