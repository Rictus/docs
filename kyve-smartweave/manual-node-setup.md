# Manual Node Setup

### Usage

There are two ways to run the node. You can either run the integration itself or run a prebuilt version of the [KYVE Node](../node/setup.md) \(recommended\).

```javascript
import SmartWeaveInstance from "@kyve/smartweave";
const poolID = ...
const stake = ...

SmartWeaveInstance(poolID, stake, wallet).run();
```

