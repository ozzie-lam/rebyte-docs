## Knowledge

Knowledge is the private data that is stored in rebyte managed vector database. Knowledge can be identified by a unique human-readable name within the user's project.

### Knowledge Types
* Local file, supported file types are:
  * "doc", "docx", "img", "epub", "jpeg", "jpg", "png", "xls", "xlsx", "ppt", "pptx", "md", "txt", "rtf", "rst", "pdf", "json", "html" "eml",
* Notion
* Discord
* GitHub

### Document
Each knowledge contains a list of documents, each document is identified by a unique document id within the knowledge.

### Chunk
Document will be chunked into multiple chunks, each chunk is identified by a unique chunk id within the document. Chunk will be sent to LLM embedding service to get the embedding vector.
When creating knowledge, user can specify the chunk size, which will determine how many chunks a document will be chunked into. Typical chunk size could be ranging from a few hundred tokens to a few thousand tokens.
