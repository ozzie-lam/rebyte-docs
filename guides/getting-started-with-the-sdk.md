# Getting Started with the SDK

## Installation

{% tabs %}
{% tab title="Typescript" %}
<pre class="language-bash"><code class="lang-bash"><strong>npm install rebyte-ts
</strong></code></pre>
{% endtab %}

{% tab title="Python" %}
```bash
pip install tryrebyte
```
{% endtab %}
{% endtabs %}

## Create a ReByteAPI

Create environment variables for your rebyte API key.

Use the API key to create a ReByteAPI.

{% tabs %}
{% tab title="Typescript" %}
```typescript
import { ReByteAPI } from 'rebyte-ts';
const {REBYTE_API_KEY} = process.env;

const rebyte = new ReByteAPI(REBYTE_API_KEY);
```
{% endtab %}

{% tab title="Python" %}
```python
import rebyte

ReByteAPI = rebyte.ReByteAPI(API_KEY)
```
{% endtab %}
{% endtabs %}
