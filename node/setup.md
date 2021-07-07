---
description: This guide will walk you trough the basics of setting up a KYVE node
---

# Setup

### Requirements

* NodeJS & Docker installed on your machine
* Arweave-Wallet with AR in it, get free AR using a faucet [here](https://faucet.arweave.net/).
* $KYVE transferred to the pools where you like to run a node.

### Clone the repository and install dependencies

1. Clone the repository

   ```text
   git clone https://github.com/KYVENetwork/kyve.git
   ```

2. Install and link dependencies

   ```text
   yarn setup
   ```

3. Switch into the node folder

   ```text
   cd integrations/node
   ```

### Create a config.json

```text
touch config.json
```

Inside your `config.json` you need to specify the pool id with the number of tokens you want to stake per pool. Your config should look like this:

```javascript
{
  "pools": {
    "B1SRLyFzWJjeA0ywW41Qu1j7ZpBLHsXSSrWLrT3ebd8": 1,
    "OFD4GqQcqp-Y_Iqh8DN_0s3a_68oMvvnekeOEu_a45I": 10
    // add further pool ids here
  }
}
```

{% hint style="info" %}
In the example above, your node would stake 1 $KYVE token in the pool with ID `B1SR..` and 10 tokens in the pool with ID `OFD4...` . You can find a list of available pools [here](https://kyve.network/gov/pools). If your account does not have enough tokens to stake in the pool, the process for the pool will fail.
{% endhint %}

### Copy your arweave key file

If you don't have an Arweave key file yet, you can create or claim one [here](https://arweave.org). We recommend renaming your key file in `arweave.json` as it is automatically covered by the `.gitignore`. Please make sure, that your wallet has a sufficient amount of AR to take part in validation or uploading. You also need $KYVE tokens to run the node. You can get $KYVE tokens [here](https://kyve.network/gov/tokens). While KYVE is running as a testnet, you can claim free tokens [here](https://kyve.network/gov/tokens).

### Create a `.env`-File

Create your `.env` file and add the following. If you disable `SEND_STATISTICS`, your node will not send any information to our Sentry. `MAINTAINER` and `NAME` are **optional**, but can help the team to reach out to you if your node runs into issues.

```text
CONFIG=config.json
WALLET=arweave.json
SEND_STATISTICS=true
MAINTAINER=foo@bar.com
NAME=my-node-name
```

_Note: If your keyfile or config-file have different names, change them accordingly_

