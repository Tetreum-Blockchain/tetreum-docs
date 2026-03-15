# Speed

Tetreum attributes its speed profile to deterministic block production under its PoA model.

## Throughput model in the source

The whitepaper defines throughput using the following variables:

- `Bₜ` = average block time
- `Tᵦ` = average transactions per block
- `TPS` = transactions per second

It then presents:

```text
TPS = Tᵦ / Bₜ
```

With the example:

```text
Tᵦ = 250
Bₜ = 5
TPS = 50 tx/sec
```

## Finality characteristics

- Block time: ~5 seconds
- Finality: deterministic, single-confirmation model
- Intended fit: real-time DeFi, gaming, and instant payment experiences
