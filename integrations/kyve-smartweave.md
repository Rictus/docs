---
description: >-
  The KYVE + SmartWeave integration, allows you to speed up your SmartWeave
  contract by using KYVE to always compute the latest state
---

# @kyve/smartweave

### Overview

The KYVE + SmartWeave node allows you to store the state from any SmartWeave contract onto Arweave. This allows the client to load a state at a given block height without calculating through every transaction.

### Config

The SmartWeave integration listens to changes happening on the contracts you specify in the config:

```javascript
{
  "contracts": ["CONTRACT_ID_1", ...]
}
```

