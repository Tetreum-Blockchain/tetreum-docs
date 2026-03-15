# Contract Deployment

Smart contracts can be deployed to the Tetreum testnet through standard JSON-RPC calls or REST-based tooling.

## Endpoints listed in the source

### JSON-RPC

`https://testrpc.testscan.com`

Supported examples include:

- `eth_sendTransaction`
- `eth_getTransactionReceipt`
- `eth_getBalance`

### REST API

`https://testnet.tetscan.com/api-docs`

The REST layer is described as providing access to contracts, blocks, transactions, tokens, and search functionality.

## Example deployment request

```bash
curl -X POST https://testrpc.testscan.com \
  -H "Content-Type: application/json" \
  -d '{
    "jsonrpc": "2.0",
    "method": "eth_sendTransaction",
    "params": [{
      "from": "0xYourAddress",
      "to": "0xTargetAddress",
      "value": "0x9184e72a000",
      "gas": "0x76c0",
      "gasPrice": "0x9184e72a000"
    }],
    "id": 1
  }'
```

## Supported SDKs and libraries listed in the source

| Language | SDK package |
| --- | --- |
| JavaScript | `@Tetreum/sdk` |
| Python | `Tetreum-python` |
| Go | `github.com/Tetreum/go-sdk` |
| Web3 compatible | `web3.js` via RPC integration |

## API rate limits listed in the source

| Access level | Rate limit | Authentication |
| --- | --- | --- |
| Public | 100 req/min/IP | No |
| Premium | 1000 req/min | API key |

> Review note: the source file also references a similar but different RPC host elsewhere. See `REVIEW-NOTES.md`.
