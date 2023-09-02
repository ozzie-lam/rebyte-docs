# 🧠 Knowledge

### Overview

Knowledge is our managed vector database which allows our users and developers to seamlessly interact with their large amount of data.

Our knowledge is designed to be easy to use, with several built-in data integration pipeline that allows users to sync up with their data warehouse dynamically.

### Structure

Each Knowledge is considered to be an independent data source. You would want to create different Knowledges for different types of data sources (Notion vs. SQL DB) or exert separate access control policies.

There is another division within each Knowledge, called Documents. Knowledge consists of a collection of Documents. You could use documents to insert the same type of data but different contents (different pages in the same Notion workspace).

### Self Managed

For the simplest upload options, we allow users to directly upload files from their computers in various formats, such as pdf, docx, and txt.&#x20;

Additionally, developers can also choose to upload and update their knowledge using our [SDK](https://github.com/tryrebyte-ai).

### Web

We provide a built-in HTTP web crawler that will recursively go through most links from the root URL. Just provide the root URL and we will automatically start the crawl.&#x20;

More on its behavior:

* We will try to get the site map from the root url, and import the first 100 urls. You can remove the ones you don't want.
* we only index first 200k characters of each page.
* it works great if your webpage is server-side rendered, but not so great if it's a SPA, we are working on it.

### Notion

The Notion integration allows users to seamlessly connect their Notion workspace. By signing in through your Notion account, and selecting the workspaces you want to connect, we will automatically sync up your selected Notion pages. This Knowledge is fully-managed, meaning that any changes from Notion will be updated dynamically to the Knowledge

### Slack

Slack integration allows users to connect their Slack message history to Knowledge. It's also a fully managed service like Notion's integration.&#x20;
