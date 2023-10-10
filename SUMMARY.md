# Table of contents

* [ReByte One Page](README.md)

## Overview

* [ReByte Concepts](overview/understanding-rebyte-architecture.md)

## Builder's Guide

* [Terminology](overview/terminology.md)
* [Agent Builder](builders-guide/agent-builder/README.md)
  * [Agent Runtime](callable/runtime.md)
  * [Prompt Template Language](callable/prompt-template-language.md)
  * [How to Chain Actions](callable/access-action-output.md)
  * [Model Action](builders-guide/agent-builder/model-action/README.md)
    * [LLM Completion](callable/actions/models/language-model.md)
    * [LLM Chat](callable/actions/models/language-model-chat.md)
  * [Data Action](builders-guide/agent-builder/data-action/README.md)
    * [Dataset Loader](callable/actions/data/dataset-loader.md)
    * [File Loader](callable/actions/data/file-loader.md)
  * [Code Action](builders-guide/agent-builder/code-action/README.md)
    * [Javascript](builders-guide/agent-builder/code-action/javascript.md)
  * [Tool Action](builders-guide/agent-builder/tool-action/README.md)
    * [Knowledge Search](callable/actions/tools/knowledge-search.md)
    * [HTTP Request](callable/actions/tools/curl-request.md)
    * [Google Search](callable/actions/tools/google-search.md)
    * [Web Scraping](callable/actions/tools/web-page-crawler.md)
  * [Control Action](builders-guide/agent-builder/control-action/README.md)
    * [Loop](callable/actions/control/loop-until.md)
    * [Parallel](callable/actions/control/map-reduce.md)
  * [Customized Action](builders-guide/agent-builder/customized-action/README.md)
    * [JsBundle Overview](extensions/jsbundle-overview.md)
* [Knowledge Pipeline](builders-guide/knowledge-pipeline/README.md)
  * [Knowledge Overview](knowledge/overview.md)
  * [Knowledge type](builders-guide/knowledge-pipeline/knowledge-type/README.md)
    * [Local Files](builders-guide/knowledge-pipeline/knowledge-type/local-files.md)
    * [Notion](builders-guide/knowledge-pipeline/knowledge-type/notion.md)
    * [GitHub](builders-guide/knowledge-pipeline/knowledge-type/github.md)
    * [Discord](builders-guide/knowledge-pipeline/knowledge-type/discord.md)
* [ChatBot UI Protocol](builders-guide/chatbot-ui-protocol/README.md)
  * [ChatBot UI Protocol](UI/overview.md)

## User's Guide

* [Team](users-guide/team/README.md)
  * [Team Overview](user/overview.md)
  * [Access Control](user/access-control.md)

## Tutorials

* [Video](tutorials/video/README.md)
  * [ReByte Overview](https://www.youtube.com/watch?v=I5BMV52Am1U)
  * [Create RAG agent in 5 minutes](https://www.youtube.com/watch?v=I5BMV52Am1U)
  * [Improve RAG](https://www.youtube.com/watch?v=CNu8ya-Raw8)
  * [Trace every step of Agent](https://www.youtube.com/watch?v=eyUt6O6u4wE)
  * [Working with external files](https://www.youtube.com/watch?v=8wQMToGqF8g)
* [Text](tutorials/text/README.md)
  * [Retrieval Augmented Generation](examples/rag.md)
  * [Internet Connected Search and Generation](examples/icsg.md)
