# Rest API Endpoints

> REST API endpoints for Tetreum Testnet explorer services.

> Tetreum Testnet is a Geth-based PoA and EVM-compatible network. REST API endpoints can be used to retrieve explorer data, chain activity, addresses, transactions, tokens, blocks, and other indexed information.

## Overview

The REST API is primarily used by the explorer interface and related services. It can also be used by developers, dashboards, analytics tools, and integrations that need indexed blockchain data.

**Explorer Base URL**

```
https://testnet.tetscan.com/
```

**REST API Base URL**

```
https://testnet.tetscan.com/api/v2
```

**API Docs**

```
https://testnet.tetscan.com/api-docs
```

## Available Data

The REST API can be used to retrieve information such as:

* blocks
* transactions
* addresses
* token transfers
* internal transactions
* logs
* smart contracts
* tokens
* chain statistics

## Related APIs

| API             | Description                                                                               |
| --------------- | ----------------------------------------------------------------------------------------- |
| Stats API       | Access pre-calculated chain statistics                                                    |
| Interpreter API | Retrieve transactions enriched with contract names, decoded methods, and readable context |

## Pagination

Tetreum Testnet REST API uses **keyset pagination** for efficient result browsing.

By default, many endpoints return the **first 50 results**.

To fetch additional results, use the `next_page_params` object returned in the response body.

## How Pagination Works

1. Request the first page from an endpoint
2. Read the `next_page_params` object in the response
3. Append those values to the next request
4. Repeat until no more results are returned

## Example

### First request

```
https://testnet.tetscan.com/api/v2/transactions
```

### Example response fragment

```json
{
  "items": [],
  "next_page_params": {
    "block_number": 123456,
    "index": 12,
    "items_count": 50
  }
}
```

### Next request

```
https://testnet.tetscan.com/api/v2/transactions?block_number=123456&index=12&items_count=50
```

## Common Endpoints

| Endpoint                                 | Description                |
| ---------------------------------------- | -------------------------- |
| `/api/v2/transactions`                   | List transactions          |
| `/api/v2/blocks`                         | List blocks                |
| `/api/v2/addresses/{address_hash}`       | Get address details        |
| `/api/v2/tokens`                         | List tokens                |
| `/api/v2/smart-contracts/{address_hash}` | Get smart contract details |
| `/api/v2/transactions/{tx_hash}`         | Get transaction details    |
| `/api/v2/blocks/{block_number_or_hash}`  | Get block details          |

## Notes

* REST API responses may be paginated
* Indexed explorer data may differ slightly from raw node RPC responses
* For wallet operations and contract interactions, use the JSON-RPC endpoint
* For explorer and analytics use cases, prefer REST API or GraphQL where available

## Network Details

```
Network Name: Tetreum Testnet
RPC URL: https://testrpc.tetreum.com
Chain ID: 793788
Currency Symbol: TET
Block Explorer URL: https://testnet.tetscan.com/
```

## Related Endpoints

**RPC URL**

```
https://testrpc.tetreum.com
```

**GraphQL URL**

```
https://testnet.tetscan.com/api/v2/graphql
```
