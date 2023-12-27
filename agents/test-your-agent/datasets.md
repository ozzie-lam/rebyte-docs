# Datasets

After designing your agent, you can test it with datasets.

You can run the dataset with the "Run Testcases" and observe the agent's response and maybe troubleshoot issues based on it.


## Dataset Creation

* Navigate to the `Datasets` tab on the top.

* Click `Create Dataset`.

* Use "Add Column" to add a new field to your dataset. "Add Row" to add a new dataset item.

<figure><img src="../../images/datasets.png" alt=""><figcaption></figcaption></figure>


## Data types supported

We support the following data types:

* String
* Number
* Boolean
* JSON Object

## Usage

Datasets can be used in two ways:

#### 1.Load data for subsequent actions

The loaded dataset can be used by subsequent actions.

This is very useful when the dataset contains example data for few shots prompting.

#### 2.Determine the input shape of the agent

The the dataset of the `Input` action determines the shape of the input of the whole agent.