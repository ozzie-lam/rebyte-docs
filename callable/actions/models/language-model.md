# Language Model

The Model Block accepts a specified prompt string and returns a Language Model completion as the result.

<figure><img src="../../../.gitbook/assets/Screenshot 2023-07-18 at 3.37.07 PM.png" alt=""><figcaption></figcaption></figure>

**Parameters:**

* **Prompt:** Enter your prompt to send to the configured model
* **Config:** Provides options for the type of LLM model and the temperature

{% hint style="info" %}
For the final model block in your callable, it must be named OUTPUT\_STREAM to stream the chat results in your copilot.
{% endhint %}

**Using Advanced Model Blocks:**

{% content-ref url="../../use-cases/utilizing-model-examples-to-convert-text-to-json.md" %}
[utilizing-model-examples-to-convert-text-to-json.md](../../use-cases/utilizing-model-examples-to-convert-text-to-json.md)
{% endcontent-ref %}
