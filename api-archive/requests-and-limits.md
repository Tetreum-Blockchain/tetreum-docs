# Requests & Limits

> API variables and rate limit information for Tetreum Testnet APIs.

Tetreum Testnet is a Geth-based PoA network. Rate limits may be updated over time to ensure RPC stability and fair usage.

## Public RPC Limits

<table data-header-hidden><thead><tr><th></th><th width="136" align="right"></th><th></th></tr></thead><tbody><tr><td><strong>Access Type</strong></td><td align="right"><strong>Rate Limit</strong></td><td><strong>Description</strong></td></tr><tr><td>Public RPC (no API key)</td><td align="right">5 req/sec</td><td>Default limit for all public requests</td></tr><tr><td>Temporary protected access</td><td align="right">5 req/sec</td><td>May be used for frontend/session-based protection if enabled</td></tr><tr><td>Individual API key</td><td align="right">10 req/sec</td><td>Optional higher limit for registered users or partners</td></tr><tr><td>Whitelisted IP</td><td align="right">25 req/sec</td><td>Higher limit for approved server IPs</td></tr><tr><td>Static instance API key</td><td align="right">10 req/sec</td><td>Optional per-instance access key</td></tr><tr><td>Admin key</td><td align="right">Unlimited</td><td>Reserved for internal infrastructure and administration</td></tr></tbody></table>

## Default Policy

* Requests without an API key are limited by IP
* Public usage is intended for wallets, developers, and light integrations
* Heavy indexing, scraping, and bulk export usage should use dedicated infrastructure
* Repeated abuse may result in temporary blocking

## Endpoint-Specific Limits

<table data-header-hidden><thead><tr><th width="513"></th><th align="right"></th><th></th></tr></thead><tbody><tr><td><strong>API Endpoint</strong></td><td align="right"><strong>Requests per Period</strong></td><td><strong>Period</strong></td></tr><tr><td><code>/api/health/*</code></td><td align="right">5</td><td>1 second</td></tr><tr><td><code>/api/v2/key</code></td><td align="right">Unlimited</td><td>—</td></tr><tr><td><code>/api/v2/import/token-info</code></td><td align="right">Unlimited</td><td>—</td></tr><tr><td><code>/api/v2/import/smart-contracts/:param</code></td><td align="right">Unlimited</td><td>—</td></tr><tr><td><code>/api/account/v2/authenticate_via_wallet</code></td><td align="right">1</td><td>1 hour</td></tr><tr><td><code>/api/account/v2/send_otp</code></td><td align="right">1</td><td>1 hour</td></tr><tr><td><code>/api/v2/tokens/:param/instances/:param/refetch-metadata</code></td><td align="right">50</td><td>1 hour</td></tr><tr><td><code>/api/v2/advanced-filters/csv</code></td><td align="right">50</td><td>1 hour</td></tr><tr><td><code>/api/v2/tokens/:param/holders/csv</code></td><td align="right">50</td><td>1 hour</td></tr><tr><td><code>/api/v2/addresses/:param/transactions/csv</code></td><td align="right">50</td><td>1 hour</td></tr><tr><td><code>/api/v2/addresses/:param/token-transfers/csv</code></td><td align="right">50</td><td>1 hour</td></tr><tr><td><code>/api/v2/addresses/:param/internal-transactions/csv</code></td><td align="right">50</td><td>1 hour</td></tr><tr><td><code>/api/v2/addresses/:param/logs/csv</code></td><td align="right">50</td><td>1 hour</td></tr><tr><td><code>/api/v2/addresses/:param/election-rewards/csv</code></td><td align="right">50</td><td>1 hour</td></tr><tr><td><code>/api/v2/smart-contracts/:param/audit-reports</code></td><td align="right">50</td><td>1 hour</td></tr></tbody></table>

## RPC Endpoint

```
https://testrpc.tetreum.com
```

## Explorer

```
https://testnet.tetscan.com/
```

## Network Details

```
Network Name: Tetreum Testnet
RPC URL: https://testrpc.tetreum.com
Chain ID: 793788
Currency Symbol: TET
Block Explorer URL: https://testnet.tetscan.com/
```

## Notes

* Tetreum Testnet is intended for testing and development
* Rate limits help keep the network stable for all users
* For higher throughput access, contact the Tetreum team
* Production integrations should avoid aggressive polling where possible
