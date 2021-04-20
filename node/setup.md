---
description: This guide will walk you trough the basics of setting up a KYVE node
---

# Setup

## Clone the Repository

Clone the node repository from our GitHub:

```
$ git clone https://github.com/KYVENetwork/node.git
```

## Create a config file

In your KYVE repository, you can configure which pools you want to support. To create your configuration, create a json file.

```bash
touch config.json
```

Inside your `config.json` you need to specify the pool id with the amount of tokens you want to stake per pool. Your config should look like this:

{% code title="config.json" %}
```bash
{
  "pools": {
    "0": 1,
    "2": 10
  }
}
```
{% endcode %}

{% hint style="info" %}
In the example above, your node would stake 1 KYVE tokens in pool with ID 0 and 10 tokens in pool with ID 2. For a list of available pools, please refer to [https://kyve.network/gov/pools](https://kyve.network/gov/pools). If your account does not have enough tokens to stake in the pool, you won't participate in the pool.
{% endhint %}

## Copy your Arweave key file

If you don't have an Arweave key file yet, you can create or claim one here \[insert link\]. We recommend renaming your key file to `arweave.json` as it is automatically covered by the `.gitignore`. Please make sure, that your wallet has a sufficient amount of AR to take part in validation or uploading. You also need KYVE tokens to run the node. You can get KYVE tokens here \[link to verto\]. While KYVE is running as a testnet, you can claim free tokens [here](https://kyve.network/gov/tokens).

## Create a `.env` file

```bash
touch .env
```

Add the following

{% code title=".env" %}
```bash
CONFIG=config.json
WALLET=arweave.json
```
{% endcode %}

{% hint style="info" %}
If you have a different name for your key file or your configuration, make sure that you supply the correct name in the `.env`
{% endhint %}



