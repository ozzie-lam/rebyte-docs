# Table of contents

* [👉 Welcome to ReByte](README.md)

## Overview

* [💡 ReByte Concepts](overview/understanding-rebyte-architecture.md)

## User Guide
* [Terminology](overview/terminology.md)
* Agent Builder
  * [Agent Runtime](callable/runtime.md)
  * [Prompt Template Language](callable/prompt-template-language.md)
  * [How to Chain Actions](callable/access-action-output.md)
  * Model Action
    * [LLM Completion](callable/actions/models/language-model.md)
    * [LLM Chat](callable/actions/models/language-model-chat.md)
  * Data Action
    * [Dataset Loader](callable/actions/data/dataset-loader.md)
    * [File Loader](callable/actions/data/file-loader.md)
  * Code Action
    * [Javascript](callable/actions/tools/jscode.md)
  * Tool Action
    * [Knowledge Search](callable/actions/tools/knowledge-search.md)
    * [HTTP Request](callable/actions/tools/curl-request.md)
    * [Google Search](callable/actions/tools/google-search.md)
    * [Web Scraping](callable/actions/tools/web-page-crawler.md)
  * Control Action
    * [Loop](callable/actions/control/loop-until.md)
    * [Parallel](callable/actions/control/map-reduce.md)
  * Customized Action
    * [JsBundle Overview](extensions/jsbundle-overview.md)

* Knowledge Pipeline
  * [Knowledge Overview](knowledge/overview.md)
  * Knowledge type
    * [Local Files](knowledge/local-files.md)
    * [Notion](knowledge/notion.md)
    * [GitHub](knowledge/github.md)
    * [Discord](knowledge/discord.md)
* ChatBot UI Protocol
  * [ChatBot UI Protocol](UI/overview.md)

## Tutorials

* Video
  * [ReByte Overview](https://www.youtube.com/watch?v=I5BMV52Am1U)
  * [Create RAG agent in 5 minutes](https://www.youtube.com/watch?v=I5BMV52Am1U)
  * [Improve RAG](https://www.youtube.com/watch?v=CNu8ya-Raw8)
  * [Trace every step of Agent](https://www.youtube.com/watch?v=eyUt6O6u4wE)
  * [Working with external files](https://www.youtube.com/watch?v=8wQMToGqF8g)
* Text
  * [Retrieval Augmented Generation](examples/rag.md)
  * [Internet Connected Search and Generation](examples/icsg.md)
