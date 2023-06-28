# Documents

## Retrieving a Document

First, find the name of the knowledge that contains the document you wish to retrieve in the knowledge tab of Cortex.

<figure><img src="../.gitbook/assets/Screenshot 2023-06-27 at 3.09.15 PM.png" alt=""><figcaption></figcaption></figure>

Then, find the name of the documentID you want to retrieve.

<figure><img src="../.gitbook/assets/Screenshot 2023-06-27 at 3.20.00 PM.png" alt=""><figcaption></figcaption></figure>

Use the knowledgeName and documentID with the `.getDocument` function of cortex to retrieve the document. See the Node.js Library for the exact .json return structure.

```javascript
try {
    const res = await cortex.getDocument('tigers','testing.txt')
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

## Uploading a Document

Find the knowledgeName of the desired location of the document.

Create an object that follows the createDocument interface to upload.

```javascript
interface createDocument {
  timestamp?: number;
  tags?: string[];
  text?: string | null;
  source_url?: string | null;
};
```

Use the documentID parameter to name the document you want to upload.

```javascript
const test = {
  "source_url": "https://www.test.com/",
  "text": "test"
  }

try {
  let output = await cortex.uploadDocument('tigers','test1',test);
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

## Deleting a Document

```javascript
try {
  let output = await cortex.deleteDocument('tigers','test1');
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
