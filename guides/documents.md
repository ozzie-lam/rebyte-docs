# Documents

## Retrieving a Document

First, find the name of the knowledge that contains the document you wish to retrieve in the knowledge tab of ReByte.

<figure><img src="../.gitbook/assets/Screenshot 2023-06-27 at 3.09.15 PM.png" alt=""><figcaption></figcaption></figure>

Then, find the name of the documentID you want to retrieve.

<figure><img src="../.gitbook/assets/Screenshot 2023-06-27 at 3.20.00 PM.png" alt=""><figcaption></figcaption></figure>

Use the knowledgeName and documentID with the `.getDocument` function of rebyte to retrieve the document. See the Node.js Library for the exact .json return structure.

{% tabs %}
{% tab title="Typescript" %}
```javascript
try {
    const res = await rebyte.getDocument('tigers','testing.txt')
    const document = res.data.document
    console.log(document.text);
} catch (error) {
    if (error.response) {
        console.log(error.response.status);
        console.log(error.response.data);
    } else {
        console.log(error.message);
    }
}
```
{% endtab %}

{% tab title="Python" %}
```python
ReByteAPI.getDocument('tigers','testing.txt')
```
{% endtab %}
{% endtabs %}

## Uploading a Document

Find the knowledgeName of the desired location of the document.

Create an object that follows the createDocument interface to upload.

{% tabs %}
{% tab title="Typescript" %}
```javascript
interface createDocument {
  timestamp?: number;
  tags?: string[];
  text?: string | null;
  source_url?: string | null;
};
```
{% endtab %}

{% tab title="Python" %}
```python
class CreateDocument:
    def __init__(
        self,
        timestamp: Union[int, None] = None,
        tags:
        List[str] = None,
        text: Union[str, None] = None,
        source_url: Union[str, None] = None
    ):
        self.timestamp = timestamp
        self.tags = tags
        self.text = text
        self.source_url = source_url
```
{% endtab %}
{% endtabs %}

Use the documentID parameter to name the document you want to upload.

{% tabs %}
{% tab title="Typescript" %}
```javascript
const test = {
  "source_url": "https://www.test.com/",
  "text": "test"
  }

try {
  let output = await rebyte.uploadDocument('tigers','test1',test);
  console.log(output.data.document);
} catch (error) {
  if (error.response) {
    console.log(error.response.status);
    console.log(error.response.data);
  } else {
    console.log(error.message);
  }
}
```
{% endtab %}

{% tab title="Python" %}
```python
test = rebyte.CreateDocument()
test.source_url = "https://www.test.com/"
test.text = "test"

ReByteAPI = rebyte.ReByteAPI("sk-...")
ReByteAPI.uploadDocument('tigers','test1',test)
```
{% endtab %}
{% endtabs %}

## Deleting a Document

{% tabs %}
{% tab title="Typescript" %}
```javascript
try {
  let output = await rebyte.deleteDocument('tigers','test1');
  console.log(output.data.document);
} catch (error:any) {
  if (error.response) {
    console.log(error.response.status);
    console.log(error.response.data);
  } else {
    console.log(error.message);
  }
}
```
{% endtab %}

{% tab title="Python" %}
```python
ReByteAPI.deleteDocument('tigers','test1')
```
{% endtab %}
{% endtabs %}
