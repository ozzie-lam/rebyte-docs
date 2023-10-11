# File Loader

Extract structure data from a file. Currently support following file types:
* "doc",
  "docx",
  "img",
  "epub",
  "jpeg",
  "jpg",
  "png",
  "xls",
  "xlsx",
  "ppt",
  "pptx",
  "md",
  "txt",
  "rtf",
  "rst",
  "pdf",
  "json",
  "html",

When user uploads a file in callable builder, rebyte will assign a unique file id to the file, and store the file content in rebyte managed storage. Assigned file id can be used in anywhere in LLM callables when referencing the file. 

In Agent UI, user can upload a file to the copilot, and copilot will pass the file id to the underlying callable.

**Parameters**:

* **File ID:** ID of the file to load from

**Output**:
  * JSON Array of structure data extracted from the file
  * Depends on file type, structure data can be different. For example, for a PDF file, the structure data is a list of pages, each page is a list of paragraphs, each paragraph is a list of lines, each line is a list of words. For a JSON file, the structure data is the JSON object itself.

**Error Handing**:
  * If the file id is invalid, or the file is not supported, the action will still return an empty array.
