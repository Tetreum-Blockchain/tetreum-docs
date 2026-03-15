# Scalability

Tetreum describes scalability as a result of separating smart contract execution from consensus and network propagation.

## Modular design

- **Execution layer:** optimized for EVM compatibility
- **Consensus layer:** lightweight PoA engine
- **Storage layer:** efficient state structures using Merkle Patricia Trees

## Performance model in the source

The whitepaper includes the following conceptual formula:

```text
Effective Throughput = f(N, V) = O(C / (L · V))
```

Where:

- `N` = number of full nodes
- `C` = total compute capacity
- `L` = latency introduced per node
- `V` = number of validators participating in consensus

## Fee behavior

The source also emphasizes:

- Fixed base-fee style behavior
- Reduced congestion spikes
- More reliable cost estimation for developers
