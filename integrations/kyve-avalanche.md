---
description: >-
  KYVE + Avalanche allows users to get permanent access to data from the
  Avalanche C-Chain
---

# @kyve/avalanche

### Overview

KYVE currently supports the archiving of the Avalanche C-Chain. You can find the current pool [here](https://kyve.network/gov/pools/0).

### Configuration

The KYVE integration listens to WebSocket events and is EVM compatible. 

{% tabs %}
{% tab title="C-Chain" %}
```javascript
{
    "endpoint": "wss://api.avax.network/ext/bc/C/ws"
}
```
{% endtab %}
{% endtabs %}



