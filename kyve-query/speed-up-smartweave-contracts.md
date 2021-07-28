# Speed up SmartWeave contracts

### Overview

### `readContract`

```typescript
const poolID = "";

// this contract needs to be present in the pool
const contractID = "";

const returnValidity = false;

const state = await readContract(
  poolID,
  contractID,
  returnValidity
);
```

### `interactRead`

