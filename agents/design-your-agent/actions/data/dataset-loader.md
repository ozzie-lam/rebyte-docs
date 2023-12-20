# Dataset Loader

The dataset loader loads data from the predefined datasets. Each agent can have multiple datasets, which can be created and edited using the dataset editor.

Each dataset is essentially a list of JSON objects with same shape. Value of each field can be following types:

* string
* number
* boolean
* object

Datasets can be used in two ways:

#### Load data for subsequent actions

When the dataset is loaded in agent, subsequent actions can access the dataset content as normal action output. This is particularly useful when the dataset contains example data for few shots prompting.

#### Determine the input shape of the agent

When the dataset is loaded in `INPUT` action, its shape determines the shape of the input of the whole agent.

<!-- **Example**

* [Dataset Loader](https://rebyte.ai/p/21b2295005587a5375d8/agent/fa56c8cf3f2080ef08d4) -->

### Spec

* **Dataset Id:** Id of the dataset to load from
