# GraphQL API

## GraphQL on Tetreum Testnet

### What is GraphQL

GraphQL is a query language for APIs that allows clients to request exactly the data they need. It provides a flexible and efficient way to access blockchain data without over-fetching unnecessary fields.

Key concepts of GraphQL:

* Hierarchical
* Strongly typed
* Client-specified queries

Advantages of GraphQL:

* Declarative data fetching
* Flexible response structure
* Efficient client integration
* Easier exploration of blockchain data

## Query Types

There are three main GraphQL operation types:

{% stepper %}
{% step %}
### Query

Used to fetch data.

```graphql
query {
  block(number: 1) {
    hash
    number
  }
}
```
{% endstep %}

{% step %}
### Mutation

Used to change data.

```graphql
mutation {
  exampleMutation(id: 1) {
    id
  }
}
```
{% endstep %}

{% step %}
### Subscription

Used to subscribe to real-time updates.

```graphql
subscription {
  newTransaction {
    hash
    blockNumber
  }
}
```
{% endstep %}
{% endstepper %}

## Access GraphQL API

You can access the Tetreum Testnet GraphQL API from the explorer interface or by using your preferred HTTP client.

**GraphQL Endpoint**

```
https://testnet.tetscan.com/api/v2/graphql
```

**Explorer**

```
https://testnet.tetscan.com/
```

You can test queries from the explorer's API section if GraphQL is enabled on the instance.

You can also use curl:

```bash
curl 'https://testnet.tetscan.com/api/v2/graphql' \
  -H 'Content-Type: application/json' \
  -d '{"query":"{ block(number: 1) { hash number } }"}'
```

## Queries

The Tetreum Testnet GraphQL API can be used to query blockchain data such as addresses, blocks, and transactions.

### Common Queries

<table><thead><tr><th width="276">Query</th><th width="145">Description</th><th>Example</th></tr></thead><tbody><tr><td><code>address(hash: AddressHash!)</code></td><td>Get an address by hash</td><td><code>{ address(hash: "0x...") { hash } }</code></td></tr><tr><td><code>addresses(hashes: [AddressHash!])</code></td><td>Get multiple addresses by hash</td><td><code>{ addresses(hashes: ["0x...", "0x..."]) { hash } }</code></td></tr><tr><td><code>block(number: Int!)</code></td><td>Get a block by number</td><td><code>{ block(number: 1) { hash number } }</code></td></tr><tr><td><code>transaction(hash: FullHash!)</code></td><td>Get a transaction by hash</td><td><code>{ transaction(hash: "0x...") { hash gasUsed } }</code></td></tr></tbody></table>

## Example Query

Example query to retrieve transactions for a specific address:

```graphql
{
  address(hash: "0x...") {
    transactions(first: 5) {
      edges {
        node {
          blockNumber
          createdContractAddressHash
          fromAddressHash
          gas
          hash
        }
      }
    }
  }
}
```

Transaction lists may support pagination arguments such as:

* `first`
* `after`
* `before`

## Notes

* GraphQL availability depends on the explorer configuration
* Tetreum Testnet is a Geth-based PoA network
* The GraphQL API is intended for development, analytics, and explorer-based queries
* For standard wallet and dApp interactions, use the JSON-RPC endpoint

## Related Endpoints

**RPC URL**

```
https://testrpc.tetreum.com
```

**Chain ID**

```
793788
```

**Currency Symbol**

```
TET
```
