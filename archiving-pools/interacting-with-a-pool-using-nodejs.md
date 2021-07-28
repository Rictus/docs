# Interacting with a pool using NodeJS

### Initialization

To interact with the pool, set up a new pool instance and insert an arweave instance, your key file, and the pool id.

```typescript
import { Pool } from "@kyve/contract-lib"

const pool = new Pool(arweave, keyfile, poolID);
```

### Deposit

Depositing allows you to transfer tokens into a pool. 

```typescript
// deposit 100 tokens into the pool
const txID = pool.deposit(100)
```

### Withdraw

Withdraw allows you to transfer tokens out of a pool. 

```typescript
// withdraw 100 tokens into the pool
const txID = pool.withdraw(100)
```

### Fund

Funding increases the pools balance. Tokens will be reduced from the funding on every payout. Requires that you have deposited tokens into the pool first.

```typescript
// fund 100 tokens into the pool
const txID = pool.fund(100)
```

### Unfund

Unfunding reduces the pool's balance. Requires that you have funded tokens into the pool first.

```typescript
// unfund 100 tokens from the pool
const txID = pool.unfund(100)
```

### Stake

Tokens will be staked. Requires that you have deposited tokens into the pool first. Staking is handled automatically when starting a node.

```typescript
// stake 100 tokens into the pool
const txID = pool.stake(100)
```



### Unstake

Tokens will be removed from the stake. Unstaking is handled automatically when starting a node.

```typescript
// remove 100 staked tokens from the pool
const txID = pool.unstake(100)
```

