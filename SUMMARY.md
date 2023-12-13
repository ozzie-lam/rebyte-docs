# Table of contents

* [👉 ReByte One Page](README.md)

## Overview

* [💡 ReByte Concepts](overview/understanding-rebyte-architecture.md)

## Builder's Guide

* [Terminology](builders-guide/terminology.md)
* [Building Agents](builders-guide/agent-builder/README.md)
  * [Agent Runtime](callable/runtime.md)
  * [Prompt Template Language](callable/prompt-template-language.md)
  * [How to Chain Actions](callable/access-action-output.md)
  * Actions
    * [Default Action](builders-guide/agent-builder/default-action/README.md)
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
      * [If Else](callable/actions/control/if-else.md)
      * [Loop](callable/actions/control/loop-until.md)
      * [Map Reduce](callable/actions/control/map-reduce.md)
    * [Early Return](callable/actions/control/early-return.md)
    * [Customized Action](builders-guide/agent-builder/customized-action/README.md)
    * [Action Extension Overview](extensions/jsbundle-overview.md)
  * [Datasets](builders-guide/building-agents/datasets/README.md)
  * [Exececution](builders-guide/building-agents/exececution/README.md)
  * [Traces](builders-guide/building-agents/traces/README.md)
  * [Version control](builders-guide/building-agents/version-control/README.md)
* [Knowledge Pipeline](builders-guide/knowledge/README.md)
  * [Knowledge Overview](builders-guide/knowledge/overview.md)
  * [Knowledge type](builders-guide/knowledge/knowledge-type/README.md)
    * [Local Files](builders-guide/knowledge/knowledge-type/local-files.md)
    * [Notion](builders-guide/knowledge/knowledge-type/notion.md)
    * [Web crawler](builders-guide/knowledge/knowledge-type/web-crawler.md)
* [ChatBot UI Protocol](builders-guide/chatbot-ui-protocol/README.md)
* [API](builders-guide/api.md)
* [Use cases](builders-guide/use-cases/README.md)
  * [Knowledge-based chatbot](builders-guide/use-cases/knowledge-based-chatbot.md)
  * [Web page summary agent](builders-guide/use-cases/web-page-summary-agent.md)
  * [Bilibili subtitle agent](builders-guide/use-cases/bilibili-subtitle-agent.md)
  * [Search engine agent](builders-guide/use-cases/search-engine-agent.md)
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
