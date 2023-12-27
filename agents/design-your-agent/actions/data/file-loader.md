# File Loader

The `File Loader` action gives you the ability to upload files to your agent.

We support various data types, including: DOC, DOCX, IMG, EPUB, JPEG, JPG, PNG, XLS, XLSX, PPT, PPTX, MD, TXT, RTF, MD, TXT, RTF, RST, PDF, JSON, HTML and EML.

## Usage

* Add a `File Loader` action to your agent and select the file you want to upload to your agent.

* Specify the `file_id` of this file and use this unique `file_id` whenever you want to refer to this file.

* If you connect your agent to an app, app users can upload files in the app, and the `file_id` will be passed to the agent.

* The output of this action is in JSON format, containing extracted data from the file. 

<!-- **Config**

* **File ID:** UUID of the file, can be fixed or reference to a variable.

**Output**

* JSON Array of structure data extracted from the file
* Depends on file type, structure data can be different. For example, for a PDF file, the structure data is a list of pages, each page is a list of paragraphs, each paragraph is a list of lines, each line is a list of words. For a JSON file, the structure data is the JSON object itself. --> 



<!-- **Example** -->

<!-- * [File Loader](https://rebyte.ai/p/21b2295005587a5375d8/agent/bb48d1c1658b5a08917a) -->

<!-- **Error Handing**

* If the file id is invalid, or the file is not supported, the action will return an empty array. -->

## Example Agent

* [File Loader](https://rebyte.ai/p/21b2295005587a5375d8/callable/bb48d1c1658b5a08917a/editor)