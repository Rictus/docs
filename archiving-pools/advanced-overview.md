# Advanced Overview

## Pool State

### Settings

#### Name & Logo

The name and logo are used for display purposes.

#### Grace Period

Measured in Arweave blocks. It determines how long a transaction will stay open for voting. The higher the grace period, the longer it takes for a transaction to be fully validated. If set too small, it can cause validators to be unable to vote on it, resulting in a transaction marked as dropped.

#### Slash Threshold

For every violation, uploaders or validators receive one slashing point. When the slashing points exceed the slash threshold, their stake gets slashed, and points are reset to 0.

#### Payout

The amount of $KYVE paid out can be configured to be dynamic or static. When the payout is dynamic pay-out is, KYVE measures the number of bytes uploaded by the uploader. The `kyvePerBytes` setting controls the number of tokens being released. If high computation is required, it makes sense to also set the `idleCost` option to release a static amount of tokens per payout.

#### Foreign Contracts

Internal setting. Linking to the governance and treasury contract.

#### Uploader

The Arweave address of the current uploader. Can be changed by the pool admins.

#### Bundle Size

The size of an [ANS-102 bundle](https://github.com/ArweaveTeam/arweave-standards/blob/master/ans/ANS-102.md), which gets stored on Arweave. Using bundles reduces costs and prevents spamming the network. The faster the incoming data stream is, the higher the bundle size should be. We recommend sending one bundle every 10 minutes. 

#### Config

A pool-specific configuration. The config object is exposed in the upload and validate functions, allowing developers to inject configurations like API endpoints into the code. Can be changed by the pool admins.

#### Credit

An internal object to keep track of a user's amount, stake, fund, and slashing points. Tokens in `amount` can be withdrawn at any time. Staked tokens are used for uploaders and validators as collateral. When their slashing points exceed the threshold, their stake gets slashed. Tokens in `fund` will be reduced every time a transaction is finalized. When there is not enough funding left in the pool, it pauses until enough tokens are in the `fund` to fulfill a payout. 

#### Transactions \(txs\)

An internal object for keeping track of a transaction's status. When the uploader uploads new data, it registers the transaction in the pool. The validator then fetches this transaction and performs the validation logic against the transaction data. The validator then submits its result to the pool. After the grace period has ended a transaction is either being dropped \(not enough validators voted\), valid or invalid. 

#### Invocations & Foreign Calls

Internal objects, used by the foreign call protocol. A SmartWeave specific protocol for interaction with other contracts.

### Example State

```text
{
  settings: {
    name: '',
    logo: '',
    foriegnContracts: {
      governance: 'cpXtKvM0e6cqAgjv-BCfanWQmYGupECt1MxRk1N9Mjk',
      treasury: 'shwdmXTFCaMq8WaCGg79oCF5GCj0bpb5tNA62cluEQY'
    },
    uploader: '3dX8Cnz3N64nKt2EKmWpKL1EbErFP3RFjxSDyQHQrkI',
    bundleSize: 1,
    gracePeriod: 20,
    slashThreshold: 5,
    payout: {
      kyvePerByte: 0.0002,
      idleCost: 0
    }
  },
  config: {
    contracts: [
      'cETTyJQYxJLVQ6nC3VxzsZf1x2-6TW2LFkGZa91gUWc'
    ]
  },
  credit: {
    vxUdiv2fGHMiIoek5E4l3M5qSuKCZtSaOBYjMRc94JU: {
      amount: 0,
      stake: 0,
      fund: 263.272,
      points: 0
    },
    '3dX8Cnz3N64nKt2EKmWpKL1EbErFP3RFjxSDyQHQrkI': {
      amount: 560.97504,
      stake: 100,
      fund: 0,
      points: 1
    },
    's-hGrOFm1YysWGC3wXkNaFVpyrjdinVpRKiVnhbo2so': {
      amount: 471.018399999999,
      stake: 100,
      fund: 0,
      points: 0
    }
  },
  txs: {
    'hH7RGiZGjKWVR1_syiBRQ_7s3kwoo-tpasWC_eK9DcA': {
      status: 'invalid',
      closesAt: 718750,
      yays: [],
      nays: [
        Array
      ],
      voters: [
        Array
      ],
      confirmedAt: 718753
    },
    EM5i8D1mYT5grk2oa3KTPpLVhlpfhfmKXH_rjMMmb7Q: {
      status: 'valid',
      closesAt: 718773,
      yays: [
        Array
      ],
      nays: [],
      voters: [
        Array
      ],
      confirmedAt: 718778
    },
    'fxRiSFH5wxjVOpPEcujmlTqM-wOAfE-yk2TikRYzYx0': {
      status: 'pending',
      closesAt: 718788,
      yays: [
        Array
      ],
      nays: [],
      voters: [
        Array
      ]
    },
  },
  invocations: [],
  foreignCalls: [
    {
      txID: 'U4HybAlJBKd0xGtTEy-SMW7RsTEvid5GTlb2BMZog_U//0',
      contract: 'cpXtKvM0e6cqAgjv-BCfanWQmYGupECt1MxRk1N9Mjk',
      input: [
        Object
      ]
    },
  ]
}
```

