# Getting Started

## Installation

```bash
npm install cortex-ts
```

## Create a CortexAPI

Create environment variables for your cortex api key and your userID.

You can find your userID in the URL when you log in.

<figure><img src="../.gitbook/assets/Screenshot 2023-06-27 at 2.58.43 PM.png" alt=""><figcaption></figcaption></figure>

```typescript
import { CortexAPI } from 'cortex-ts';
const {CORTEX_API_KEY, USER_ID} = process.env;

const cortex = new CortexAPI(CORTEX_API_KEY,USER_ID);
```
