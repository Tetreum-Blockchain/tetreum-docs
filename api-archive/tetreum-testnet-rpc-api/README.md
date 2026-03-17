# Tetreum Testnet RPC API

## Tetreum Testnet ETH RPC Methods Reference

Complete reference for Ethereum JSON-RPC methods available on **Tetreum Testnet**.

## Quick Reference

Tetreum Testnet is a **Geth-based PoA network** and provides an **EVM-compatible JSON-RPC endpoint**.

**RPC Endpoint**

`https://testrpc.tetreum.com`

**Explorer**

`https://testnet.tetscan.com/`

**Network Details**

* **Network Name:** Tetreum Testnet
* **Chain ID:** `793788`
* **Currency Symbol:** `TET`
* **Consensus:** PoA
* **Client:** Geth

## Wallet Configuration

```
Network Name: Tetreum Testnet
RPC URL: https://testrpc.tetreum.com
Chain ID: 793788
Currency Symbol: TET
Block Explorer URL: https://testnet.tetscan.com/
```

## Methods Overview

### Read Operations

| Method                    | Description             | Parameters               |
| ------------------------- | ----------------------- | ------------------------ |
| `eth_blockNumber`         | Get latest block number | None                     |
| `eth_getBalance`          | Get account balance     | address, block           |
| `eth_getTransactionCount` | Get nonce               | address, block           |
| `eth_getCode`             | Get contract bytecode   | address, block           |
| `eth_getStorageAt`        | Get storage value       | address, position, block |
| `eth_gasPrice`            | Get current gas price   | None                     |
| `eth_chainId`             | Get chain ID            | None                     |

### Transaction Operations

| Method                      | Description               | Parameters |
| --------------------------- | ------------------------- | ---------- |
| `eth_getTransactionByHash`  | Get transaction details   | hash       |
| `eth_getTransactionReceipt` | Get transaction receipt   | hash       |
| `eth_sendRawTransaction`    | Submit signed transaction | signedData |

### Block Operations

| Method                 | Description         | Parameters          |
| ---------------------- | ------------------- | ------------------- |
| `eth_getBlockByNumber` | Get block by number | blockNumber, fullTx |
| `eth_getBlockByHash`   | Get block by hash   | blockHash, fullTx   |

### Call Operations

| Method            | Description           | Parameters         |
| ----------------- | --------------------- | ------------------ |
| `eth_call`        | Execute contract call | transaction, block |
| `eth_estimateGas` | Estimate gas cost     | transaction, block |

### Log Operations

| Method        | Description    | Parameters |
| ------------- | -------------- | ---------- |
| `eth_getLogs` | Get event logs | filter     |

{% stepper %}
{% step %}
### eth\_blockNumber

**Purpose:** Get the latest block number.

```json
{
  "jsonrpc": "2.0",
  "method": "eth_blockNumber",
  "params": [],
  "id": 1
}
```

```json
{
  "jsonrpc": "2.0",
  "result": "0x123456",
  "id": 1
}
```
{% endstep %}

{% step %}
### eth\_getBalance

**Purpose:** Get account balance.

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBalance",
  "params": [
    "0x0000000000000000000000000000000000000000",
    "latest"
  ],
  "id": 1
}
```

```json
{
  "jsonrpc": "2.0",
  "result": "0x0",
  "id": 1
}
```
{% endstep %}

{% step %}
### eth\_getLogs

**Purpose:** Get matching event logs.

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getLogs",
  "params": [
    {
      "address": "0x0000000000000000000000000000000000000000",
      "fromBlock": "0x1",
      "toBlock": "latest",
      "topics": []
    }
  ],
  "id": 1
}
```

```json
{
  "jsonrpc": "2.0",
  "result": [],
  "id": 1
}
```
{% endstep %}

{% step %}
### eth\_gasPrice

**Purpose:** Get current gas price.

```json
{
  "jsonrpc": "2.0",
  "method": "eth_gasPrice",
  "params": [],
  "id": 1
}
```

```json
{
  "jsonrpc": "2.0",
  "result": "0x3b9aca00",
  "id": 1
}
```
{% endstep %}

{% step %}
### eth\_getTransactionByHash

**Purpose:** Get transaction details by hash.

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getTransactionByHash",
  "params": [
    "0x88df016429689c079f3b2f6ad39fa052532c56795b733da78a91ebe6a713944b"
  ],
  "id": 1
}
```

```json
{
  "jsonrpc": "2.0",
  "result": {
    "hash": "0x88df016429689c079f3b2f6ad39fa052532c56795b733da78a91ebe6a713944b",
    "from": "0x...",
    "to": "0x...",
    "value": "0x...",
    "gas": "0x...",
    "gasPrice": "0x...",
    "input": "0x...",
    "nonce": "0x...",
    "blockNumber": "0x...",
    "blockHash": "0x...",
    "transactionIndex": "0x..."
  },
  "id": 1
}
```
{% endstep %}

{% step %}
### eth\_getTransactionReceipt

**Purpose:** Get transaction receipt.

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getTransactionReceipt",
  "params": [
    "0x88df016429689c079f3b2f6ad39fa052532c56795b733da78a91ebe6a713944b"
  ],
  "id": 1
}
```

```json
{
  "jsonrpc": "2.0",
  "result": {
    "transactionHash": "0x88df...",
    "transactionIndex": "0x1",
    "blockHash": "0x...",
    "blockNumber": "0x...",
    "from": "0x...",
    "to": "0x...",
    "cumulativeGasUsed": "0x...",
    "gasUsed": "0x5208",
    "contractAddress": null,
    "logs": [],
    "logsBloom": "0x...",
    "status": "0x1"
  },
  "id": 1
}
```
{% endstep %}

{% step %}
### eth\_chainId

**Purpose:** Get chain ID.

```json
{
  "jsonrpc": "2.0",
  "method": "eth_chainId",
  "params": [],
  "id": 1
}
```

```json
{
  "jsonrpc": "2.0",
  "result": "0xc1d5c",
  "id": 1
}
```
{% endstep %}

{% step %}
### eth\_getTransactionCount

**Purpose:** Get nonce for an address.

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getTransactionCount",
  "params": [
    "0x0000000000000000000000000000000000000000",
    "latest"
  ],
  "id": 1
}
```

```json
{
  "jsonrpc": "2.0",
  "result": "0x0",
  "id": 1
}
```
{% endstep %}

{% step %}
### eth\_getCode

**Purpose:** Get bytecode at an address.

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getCode",
  "params": [
    "0x0000000000000000000000000000000000000000",
    "latest"
  ],
  "id": 1
}
```

```json
{
  "jsonrpc": "2.0",
  "result": "0x",
  "id": 1
}
```
{% endstep %}

{% step %}
### eth\_getStorageAt

**Purpose:** Get value from storage position.

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getStorageAt",
  "params": [
    "0x0000000000000000000000000000000000000000",
    "0x0",
    "latest"
  ],
  "id": 1
}
```

```json
{
  "jsonrpc": "2.0",
  "result": "0x0000000000000000000000000000000000000000000000000000000000000000",
  "id": 1
}
```
{% endstep %}

{% step %}
### eth\_estimateGas

**Purpose:** Estimate gas cost.

```json
{
  "jsonrpc": "2.0",
  "method": "eth_estimateGas",
  "params": [
    {
      "from": "0x0000000000000000000000000000000000000000",
      "to": "0x0000000000000000000000000000000000000000",
      "value": "0x0"
    },
    "latest"
  ],
  "id": 1
}
```

```json
{
  "jsonrpc": "2.0",
  "result": "0x5208",
  "id": 1
}
```
{% endstep %}

{% step %}
### eth\_getBlockByNumber

**Purpose:** Get block information by number.

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockByNumber",
  "params": ["latest", false],
  "id": 1
}
```

```json
{
  "jsonrpc": "2.0",
  "result": {
    "number": "0x123456",
    "hash": "0x...",
    "parentHash": "0x...",
    "timestamp": "0x...",
    "transactions": ["0x..."],
    "gasLimit": "0x...",
    "gasUsed": "0x...",
    "miner": "0x..."
  },
  "id": 1
}
```
{% endstep %}

{% step %}
### eth\_getBlockByHash

**Purpose:** Get block information by hash.

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockByHash",
  "params": [
    "0x9b83c12c69edb74f6c8dd5d052765c1adf940e320bd1291696e6fa07829eee71",
    false
  ],
  "id": 1
}
```
{% endstep %}

{% step %}
### eth\_sendRawTransaction

**Purpose:** Submit a signed transaction.

```json
{
  "jsonrpc": "2.0",
  "method": "eth_sendRawTransaction",
  "params": [
    "0xf86c098504a817c800825208943535353535353535353535353535353535353535880de0b6b3a76400008025a028ef61340bd939bc2195fe537567866003e1a15d3c71ff63e1590620aa636276a067cbe9d8997f761aecb703304b3800ccf555c9f3dc64214b297fb1966a3b6d83"
  ],
  "id": 1
}
```

```json
{
  "jsonrpc": "2.0",
  "result": "0xe670ec64341771606e55d6b4ca35a1a6b75ee3d5145a99d05921026d1527331",
  "id": 1
}
```
{% endstep %}

{% step %}
### eth\_call

**Purpose:** Execute a contract call without creating a transaction.

```json
{
  "jsonrpc": "2.0",
  "method": "eth_call",
  "params": [
    {
      "to": "0x0000000000000000000000000000000000000000",
      "data": "0x"
    },
    "latest"
  ],
  "id": 1
}
```

```json
{
  "jsonrpc": "2.0",
  "result": "0x",
  "id": 1
}
```
{% endstep %}
{% endstepper %}

## Usage Tips

### Batch Requests

```json
[
  {
    "jsonrpc": "2.0",
    "method": "eth_blockNumber",
    "params": [],
    "id": 1
  },
  {
    "jsonrpc": "2.0",
    "method": "eth_gasPrice",
    "params": [],
    "id": 2
  }
]
```

### Error Handling

```json
{
  "jsonrpc": "2.0",
  "error": {
    "code": -32602,
    "message": "Invalid params"
  },
  "id": 1
}
```

* `-32700` = Parse error
* `-32600` = Invalid request
* `-32601` = Method not found
* `-32602` = Invalid params
* `-32603` = Internal error
