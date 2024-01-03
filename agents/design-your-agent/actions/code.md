# Code 

The  `Code` action is a very frequently
 used action. It allows you to write Javascript code to process the data from previous actions in any way you want.

## Usage

**General Usage**

* To use the `Code` action, first add a `Code` action to your agent.

* Write any Javascript code here to process the data from previous actions and to send data to the next actions.

**Cache**

* There's a `cache` button on the top right of the `Code` action. If you turn it on, the results will be cached. If the input of `Code` action and the code are the same, the results will be returned directly from the cache. This can greatly improve the performance of your agent.

## Example 

<figure><img src="../../../images/code-1.png"></figure>

* For example, if the `MODEL_CALL` action returned a message containing a JSON string like this:`"{"location":"New York","weather":"parly couldy","temperatuee":"43"}"`.

* And you want to get the "temperature" field from this JSON. You can add a `Code` action(named "CODE_1") and write the following code:

```javascript
const _fun = (env) => {
  var jsonString = env.state.MODEL_CALL.message.content;
  var jsonObject = JSON.parse(jsonString);
  var temperature = jsonObject.temperature;
  return tempe
}
```

<figure><img src="../../../images/code-2.png"></figure>

* Now you can use {{CODE_1}} or env.state.CODE_1 to get the value of the "temperature" field.

<figure><img src="../../../images/code-3.png"></figure>

  

