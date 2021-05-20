# Overview

### About

The KYVE + SmartWeave node allows you to store the state from any SmartWeave contract onto Arweave. This allows the client to load a state a given block height without the need to calculate through every transaction.

### Using KYVE to store a contract state

#### Create a pool

1. Go to the[ pools overview](https://kyve.network/gov/pools)  
2. Click on "Add new"  
3. Fill in a name and select SmartWeave as the architecture.  
4. Fill in the pool config as explained[ below](overview.md#config).  
5. Click on "Create Pool"

{% hint style="info" %}
It takes around 5-30 minutes for the pool to be visible in the overview
{% endhint %}

#### Pool setup

1. Make sure that you have staked $KYVE in the [vault](https://kyve.network/gov/vault)
2. Click on the pool you have created
3. Click on the pencil icon to update the pool
4. Select `1` as `bundleSize`
5. Set `3dX8Cnz3N64nKt2EKmWpKL1EbErFP3RFjxSDyQHQrkI` as the uploader \(you can also choose another node address\)
6. Click on "Propose Vote"
7. Wait for the vote to be created \(this might take 5-10 minutes\)
8. Click on the "Votes" tab inside your pool
9. Vote with "yay"
10. After 100 Block the vote is complete \(~3 hours\)
11. Click on "Finalize" 

### Config

The SmartWeave integration listens to changes happening on the contracts you specify in the config:

```javascript
{
  "contracts": ["CONTRACT_ID_1", ...]
}
```

