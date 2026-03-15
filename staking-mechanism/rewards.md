# Rewards

Rewards are calculated when a matured position is withdrawn.

## Formula

```text
Reward = (amount × pool.percent) / 100
```

## Example shown in the source

```text
Reward = (1000 × 30) / 100 = 300 TET
```

## Additional reward rules

- Early withdrawal is not allowed
- Rewards cannot exceed the available `totalRewards` pool
- Users can inspect staking positions with query functions such as `getUserStakes()` and `getStakeDetails()`

> Review note: the source lists the 180-day pool once as **50%** and later gives a reward example using **30%**. Confirm the intended value before publishing.
