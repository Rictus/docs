---
description: This guide will walk you trough the basics of setting up a KYVE node
---

# Setup

### Requirements

* NodeJS, YARN & Docker installed on your machine
* Arweave-Wallet with AR in it, get free AR using a faucet [here](https://faucet.arweave.net/).

### Clone the repository and install dependencies

1. Clone the repository

   ```text
   git clone https://github.com/KYVENetwork/kyve.git
   ```

2. Switch into the main directory

   ```text
   cd kyve
   ```

3. Install and link dependencies

   ```text
   yarn setup
   ```

4. Switch into the node folder

   ```text
   cd integrations/node
   ```

### Create a config.json

```text
touch config.json
```

Inside your `config.json` you need to **specify** the **pool address** with the **number of tokens** you want to stake per pool. Your config should look like this:

{% code title="config.json" %}
```javascript
{
  "pools": {
    "0xbBBfbE9A731634eDdf84C67A106CEE1F981F3f7e": 10
  }
}
```
{% endcode %}

{% hint style="info" %}
In the example above, your node would stake 10 $KYVE token in the pool with address `0xbBBf...` . You can find a list of available pools [here](https://app.kyve.network). If your account does not have enough tokens to stake in the pool, the process for the pool will fail.
{% endhint %}

### Copy your arweave key file

If you don't have an Arweave key file yet, you can create or claim one [here](https://arweave.org). We recommend renaming your key file in `arweave.json` as it is automatically covered by the `.gitignore`. Please make sure, that your wallet has a sufficient amount of AR to take part in validation or uploading. You also need $KYVE tokens to run the node. You can get $KYVE tokens [here](../usdkyve-token.md#get-free-tokens). While KYVE is running as a testnet, you can claim free tokens [here](../usdkyve-token.md#get-free-tokens).

### Create a `.env`-File

```text
touch .env
```

Create your `.env` file and add the following. If you disable `SEND_STATISTICS`, your node will not send any information to our Sentry. `MAINTAINER` and `NAME` are **optional**, but can help the team to reach out to you if your node runs into issues.

```text
CONFIG=config.json
WALLET=arweave.json
PK=0x...
SEND_STATISTICS=true
MAINTAINER=foo@bar.com
NAME=my-node-name
```

{% hint style="info" %}
_If your key file or config-file have different names, change them accordingly_
{% endhint %}

