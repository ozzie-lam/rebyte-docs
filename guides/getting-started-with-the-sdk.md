# Getting Started with the SDK

## Installation

{% tabs %}
{% tab title="Typescript" %}
<pre class="language-bash"><code class="lang-bash"><strong>npm install cortex-ts
</strong></code></pre>
{% endtab %}

{% tab title="Python" %}
```bash
pip install trycortex-py
```
{% endtab %}
{% endtabs %}

## Create a CortexAPI

Create environment variables for your cortex API key.

Use the API key to create a CortexAPI.

{% tabs %}
{% tab title="Typescript" %}
```typescript
import { CortexAPI } from 'cortex-ts';
const {CORTEX_API_KEY} = process.env;

const cortex = new CortexAPI(CORTEX_API_KEY);
```
{% endtab %}

{% tab title="Python" %}
```python
import cortex

CortexAPI = cortex.CortexAPI(API_KEY)
```
{% endtab %}
{% endtabs %}
