# @kyve/zilliqa

### Overview

The KYVE + Zilliqa node allows you to bridge any data stream from a Zilliqa chain onto Arweave.

### Config

The Zilliqa integration uses the WebSocket endpoint to listen to the latest block data. For more information, please have a look at their [documentation](https://dev.zilliqa.com/docs/dev/dev-tools-websockets/).

{% tabs %}
{% tab title="Mainnet" %}
```javascript
{
  "endpoint": "wss://api-ws.zilliqa.com",
  "api": "https://api.zilliqa.com/"
}
```
{% endtab %}

{% tab title="Custom" %}
```javascript
{
  "endpoint": "wss://....",
  "api": "https://...."
}
```
{% endtab %}
{% endtabs %}



