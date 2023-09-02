# ⚡ Making your first Callable

{% hint style="info" %}
Callable is currently in private preview, only selected developers and customers have access to Callable Builder. If you'd like to submit a request please contact rebyte@kinesys.ai!
{% endhint %}

Callable is the serverless function that powers each copilot, or any of your AI workflows. Let's build a Callable today that helps recommend movies to watch!&#x20;

## 1. Create a knowledge

One of the powerful features of ReByte is to let AI interact with your own data. Knowledge is where you store your data.&#x20;

Head to the knowledge tab here and create a knowledge

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

ReByte supports multiple upload options. Let's use Web as our options. Enter the Knowledge name and description and go to the the next step

<figure><img src="../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>

Enter the url of Rotten Tomateo: [https://editorial.rottentomatoes.com/](https://editorial.rottentomatoes.com/). Follow the rest of the set up and your knowledge should be ready to go! &#x20;

<figure><img src="../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Give the knowledge upload process a few minutes to fully sync up. You can continue to the next step, the sync up process will continue to run in the background.
{% endhint %}

### 2. Create Callable

Navigate to Callable Builder and create a callable. Enter the name, description, and set the visibility. We will use "Chat" callable template, which is configured to work with Chat copilot.

<figure><img src="../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

Go to the RETRIEVALS block, and select rotten-tomateo as your knowledge. You could select multiple knowledge if you have more information.&#x20;

<figure><img src="../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

You are almost there! Now the last thing to edit would be the prompt that passed into the language model. Let's modify the prompt in the language model block called OUTPUT\_STREAM to this:

```atom
You are an expert of movies. Please answer this following question: {{EXTRACT_QUESTION}}, base on following content:
{{RETRIEVALS_RESULT}}
Please answer the questions with the best of your knowledge. If not, please ask more questions for more information and recommend with some suggestions based on common knowledge.
You can make up an answer if you really cannot answer the question.

let's begin!
```

Let's also set the Max Tokens to around 2000.

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

### 3. Test your Callable

We've configured our Callable. But how do we know if it will work well? Let's create some test datasets. Go to the Datasets tab and go into ChatDataset.

<figure><img src="../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

You can write a few new test cases like this:

<figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

Now you are good to run tests! Go back to Design tab and click Run TestCases.&#x20;

Results from each block will be displayed below each block. We can go to the final OUTPUT block to check if the final results look good.&#x20;

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

### 4. Deploy!

When you feel confident about your Callable's results, hit Deploy on the right top corner. The API for running this callable will be instantly generated, and now can integrate this into your product!

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Remember to always run TestCases before hitting Deploy. After editing your Callable, If you don't run TestCases, Deploy won't freeze your edits into the next version. If you see that the version number hasn't incremented after Deploy, that means there is no new changes being added in production. Try run TestCases and then Deploy.
{% endhint %}

### 5. Running it with a Copilot (optional)

You could directly consume the Callable API from your project, or you can connect a copilot to this callable and start chatting with it immediately.

Create a new Copilot and configure it as such to connect to the callable.

<figure><img src="../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>

Congratulations! Now you should be able to directly chat with your movie recommendation assistant.

<figure><img src="../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>
