# Loop Until

This action will run the actions inside the loop until the condition is met. The condition is a javascript code that returns a boolean value. The code can reference the output of previous actions by using the `env.state.ACTION_NAME` syntax. For example, if the previous block is named `ACTION_1`, then the code can reference the output of `ACTION_1` by using `env.state.ACTION_1`.