# Utilizing Model Examples to Convert Text to JSON

## Basic Model Block

The basic Model Block accepts a specified prompt string and returns a Language Model completion as the result.

<figure><img src="../.gitbook/assets/Screenshot 2023-07-18 at 3.37.07 PM.png" alt=""><figcaption></figcaption></figure>

## Advanced Model Block

The advanced Model Block provides parameters for the Introduction and Examples

* **Introduction:** A paragraph that will appear at the beginning of your prompt once. Provides instruction to the model about how it should interpret your examples
* **Examples:** Provide examples of the type of response you want the model to output. This could be a list of examples that are organized as a template question and answer.
* **Prompt:** The final question that will appear at the end of the prompt that the user wants the model to complete.

<figure><img src="../.gitbook/assets/Screenshot 2023-07-18 at 3.18.07 PM (1).png" alt=""><figcaption></figcaption></figure>

## Converting Text to JSON

In order to create a callable that can change plain text into a JSON, we need to provide examples for our model to reference back to so that the model would know what kind of output we are looking for.

To do this, let's initialize our examples as an array of example objects with a question and an answer field. There are two ways to do this, the first way will use a code block.

<figure><img src="../.gitbook/assets/Screenshot 2023-07-18 at 4.09.06 PM.png" alt=""><figcaption></figcaption></figure>

We can also load examples using the Data Block and inputting the examples in the dataset tab.&#x20;

<figure><img src="../.gitbook/assets/Screenshot 2023-07-18 at 5.18.51 PM.png" alt=""><figcaption></figcaption></figure>

That uses the following example dataset.

<figure><img src="../.gitbook/assets/Screenshot 2023-07-18 at 5.25.16 PM.png" alt=""><figcaption></figcaption></figure>

After initializing the examples, we can now set up an advanced language model block that has an introduction that describes our desired task to our model and then enter in our examples as a question followed by an answer. Finally, we enter our original input question as our prompt.

<figure><img src="../.gitbook/assets/Screenshot 2023-07-18 at 4.10.36 PM.png" alt=""><figcaption></figcaption></figure>

We can now run some test cases to see if this works. When we try the input:

<figure><img src="../.gitbook/assets/Screenshot 2023-07-18 at 5.12.57 PM (1).png" alt=""><figcaption></figcaption></figure>

We can see that our callable successful returns the JSON object as:

<figure><img src="../.gitbook/assets/Screenshot 2023-07-18 at 5.13.21 PM.png" alt=""><figcaption></figcaption></figure>

Once tested, deploy the callable to use in any application.
