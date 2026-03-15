# How It Works

The staking contract is described as a pool-based mechanism where each pool has a lock duration and a reward percentage.

## Mechanics

- Users select a pool based on duration
- Tokens are deposited through `stake()`
- The contract tracks the stake and its maturity
- Rewards are added at withdrawal if the lock period is complete

## Example pools listed in the source

```solidity
pools[1] = Pool(30 days, 5%);
pools[3] = Pool(90 days, 20%);
pools[6] = Pool(180 days, 50%);
```

## Example stake structure

```solidity
struct Stake {
    uint256 poolId;
    uint256 amount;
    uint256 startTime;
}
```

The source describes the contract as non-custodial, open-source, and designed for transparent inspection.
