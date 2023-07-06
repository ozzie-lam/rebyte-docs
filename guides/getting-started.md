# Getting Started

## Installation

```bash
npm install cortex-ts
```

## Create a CortexAPI

Create environment variables for your cortex API key.

Use the API key to create a CortexAPI.

```typescript
import { CortexAPI } from 'cortex-ts';
const {CORTEX_API_KEY} = process.env;

const cortex = new CortexAPI(CORTEX_API_KEY);
```
