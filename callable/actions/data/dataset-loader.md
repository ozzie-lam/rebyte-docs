# Dataset Loader

Loads Data from the Predefined Dataset. Each callable can have multiple datasets, dataset can be created or edited using dataset editor.

Each dataset is essentially a list of JSON objects with same shape. Value of each field can be following types:
* **string**
* **number**
* **boolean**
* **array**
* **object**

Dataset can be used in the two ways:
#### Load data for subsequent actions
when a dataset is loaded in callable, subsequent actions can access the dataset content as normal action output. This is particularly useful when the dataset contains example data for few shots prompt.
#### Determine the input shape of the callable
when dataset is loaded in INPUT action, its shape determines the shape of the input of the whole callable.

### Spec
* **Dataset Id:** Id of the dataset to load from

