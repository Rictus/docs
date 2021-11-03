---
description: >-
  This guide will walk you through the basics of running the KYVE + Cosmos
  integration.
---

# Running the Cosmos integration

## Requirements

- Ethereum wallet (MetaMask)
- You need $DEV and $KYVE (You can get some for free [here](https://app.kyve.network/faucet))
- Any device with a good internet connection

## Docker (Recommended)

You can run the Cosmos integration directly from Docker.

To pull the latest Docker image, run:

```
docker pull kyve/cosmos:latest
```

And to start your node, run the following (don't forget to pass in [options](running.md#options)):

```
docker run --name kyve-cosmos-node kyve/cosmos:latest --pool POOL_ADDRESS --private-key PRIVATE_KEY --stake 100
```

## Prebuilt Binaries

We also provide prebuilt binaries for you to run.

We currently support Linux, macOS, and Windows binaries - which you can download from [here](https://github.com/KYVENetwork/cosmos/releases).

To run a binary, all you need to do is specify your [options](running.md#options).

### Run on Linux

```
./kyve-cosmos-linux --pool POOL_ADDRESS --private-key PRIVATE_KEY --stake 100
```

### Run on MacOS

```
./kyve-cosmos-macos --pool POOL_ADDRESS --private-key PRIVATE_KEY --stake 100
```

### Run on Windows

```
.\kyve-cosmos-win.exe --pool POOL_ADDRESS --private-key PRIVATE_KEY --stake 100
```

## Options

**`-p, --pool <string>`**

The address of the pool you want to run on.

**`-s, --stake <number>`**

The amount of tokens you want to stake.

**`-pk, --private-key <string>`**

Your Ethereum private key that holds $KYVE.

**`-k, --keyfile <string>` \_optional**\_

The path to your Arweave keyfile.

**`-n, --name <string>` \_optional, default is a random name**\_

The identifier name of the node.

**`-e, --endpoint <string>` \_optional**\_

A custom Moonbase Alpha endpoint.

**`-g, --gas-multiplier <string>` \_optional**\_

The amount that you want to multiply the default gas price by.

**`-st, --send-statistics <boolean>` \_optional, default is true**\_

Send statistics.

## Verify a node is running correctly

### Uploader

When you run as an uploader you should see something like:

```
2021-11-03 09:41:00.000  INFO 🚀 Starting node ...
    Name          = kyve-cosmos-uploader
    Address       = 0x...
    Pool          = 0x...
    Desired Stake = 100 $KYVE
    Version       = v0.0.0
2021-11-03 09:41:00.000  DEBUG [Metadata] Attempting to fetch the metadata.
2021-11-03 09:41:00.000  DEBUG [Metadata] Successfully fetched the metadata.
2021-11-03 09:41:00.000  DEBUG [Settings] Attempting to fetch the settings.
2021-11-03 09:41:00.000  DEBUG [Settings] Successfully fetched the settings.
2021-11-03 09:41:00.000  DEBUG [Config] Attempting to fetch the config.
2021-11-03 09:41:00.000  DEBUG [Config] Successfully fetched the config.
2021-11-03 09:41:00.000  INFO 💻 Running node on runtime @kyve/cosmos.
2021-11-03 09:41:00.000  DEBUG [Stake] Attempting to stake 100 $KYVE.
2021-11-03 09:41:00.000  DEBUG [Stake] Approving 100 $KYVE to be spent. Transaction = 0x...
2021-11-03 09:41:00.000  INFO [Stake] 👍 Successfully approved.
2021-11-03 09:41:00.000  DEBUG [Stake] Staking 100 $KYVE. Transaction = 0x...
2021-11-03 09:41:00.000  INFO [Stake] 📈 Successfully staked.
2021-11-03 09:41:00.000  INFO [Cosmos] ✅ Connection created. Endpoint = wss://rpc.cosmos.network
```

### Validator

When you run as a validator you should see something like:

```
2021-11-03 09:41:00.000  INFO 🚀 Starting node ...
    Name          = kyve-cosmos-validator
    Address       = 0x...
    Pool          = 0x...
    Desired Stake = 100 $KYVE
    Version       = v0.0.0
2021-11-03 09:41:00.000  DEBUG [Metadata] Attempting to fetch the metadata.
2021-11-03 09:41:00.000  DEBUG [Metadata] Successfully fetched the metadata.
2021-11-03 09:41:00.000  DEBUG [Settings] Attempting to fetch the settings.
2021-11-03 09:41:00.000  DEBUG [Settings] Successfully fetched the settings.
2021-11-03 09:41:00.000  DEBUG [Config] Attempting to fetch the config.
2021-11-03 09:41:00.000  DEBUG [Config] Successfully fetched the config.
2021-11-03 09:41:00.000  INFO 💻 Running node on runtime @kyve/cosmos.
2021-11-03 09:41:00.000  DEBUG [Stake] Attempting to stake 100 $KYVE.
2021-11-03 09:41:00.000  DEBUG [Stake] Approving 100 $KYVE to be spent. Transaction = 0x...
2021-11-03 09:41:00.000  INFO [Stake] 👍 Successfully approved.
2021-11-03 09:41:00.000  DEBUG [Stake] Staking 100 $KYVE. Transaction = 0x...
2021-11-03 09:41:00.000  INFO [Stake] 📈 Successfully staked.
```
