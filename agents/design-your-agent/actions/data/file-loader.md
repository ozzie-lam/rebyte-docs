# File Loader

Extract structure data from a file. Currently support following file types: DOC, DOCX, IMG, EPUB, JPEG, JPG, PNG, XLS, XLSX, PPT, PPTX, MD, TXT, RTF, MD, TXT, RTF, RST, PDF, JSON, HTML, EML

When user uploads a file in agent builder, rebyte will assign a unique **file id** to the file, and store the file content in our storage. Assigned file id can be used in anywhere in LLM agents when using this file.

When using ReByte apps, users can upload files, and the app will pass the **file id** to the underlying agent.

**Config**

* **File ID:** UUID of the file, can be fixed or reference to a variable.

**Output**

* JSON Array of structure data extracted from the file
* Depends on file type, structure data can be different. For example, for a PDF file, the structure data is a list of pages, each page is a list of paragraphs, each paragraph is a list of lines, each line is a list of words. For a JSON file, the structure data is the JSON object itself.

<!-- **Example** -->

<!-- * [File Loader](https://rebyte.ai/p/21b2295005587a5375d8/agent/bb48d1c1658b5a08917a) -->

**Error Handing**

* If the file id is invalid, or the file is not supported, the action will return an empty array.
