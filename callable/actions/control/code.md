# Code

Code blocks allow for users to execute JavaScript code in a Callable

<figure><img src="../../../.gitbook/assets/Screenshot 2023-07-24 at 4.07.04 PM.png" alt=""><figcaption></figcaption></figure>

The env variable passed into the function allows for referencing previous block outputs inside the Code Block. It uses the syntax `env.state.BLOCK_NAME` to reference a block by its name. In the example above, the block name for the code block would be `CODE_1`. User's can name blocks anything as long as it is unique inside the Callable.
