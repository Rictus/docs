# $KYVE Token

{% hint style="danger" %}
KYVE is running is testnet.

Tokens do **not** have any value, and can **not** be traded on exchanges.
{% endhint %}

### Overview

$KYVE is used in the protocol for staking, voting, and rewarding uploaders and validators for participating in the network.

Ways to earn tokens as a user:

* Earn staking rewards by being an uploader or a validator
* Earn staking rewards by having staked tokens in the governance
* Earn tokens by getting them transferred from you through the treasury
* Buy/Sell tokens from an exchange

### Token flow

The KYVE architecture consists of three main parts:

#### Governance

In the Governance Smart-Contract, users can stake $KYVE. Staking $KYVE allows users to participate in voting on the protocol. Every user who has staked tokens has the chance of receiving tokens as a reward. The higher the stake, the higher the chance of receiving a reward is.

#### Treasury

Only governance votes can control the treasury contract, and it will always receive 1% of tokens payouts. The governance can vote on transferring tokens out of the treasury.

#### Pools

There can be multiple pools. Nodes must stake in the pool. Nodes can have two types: Uploader or Validator. Once the uploader has uploaded data and registered it in the pool, the validators fetch the data and validate it. After a grace period is over, the amount of $KYVE to be paid out is calculated. The reward will be paid out to a governance holder, the treasury, the uploader, and the validators. The validator reward gets evenly distributed between all validators.
