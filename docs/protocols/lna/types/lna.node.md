# lna.node

This object contains information about a Lightning Network node.

## Payload fields

| Name          | Type      | Description                                                      |
|---------------|-----------|------------------------------------------------------------------|
| Alias         | string    | The node's self-reported alias from the Lightning Network.       |
| Color         | string    | The node's advertised color as a hex string (e.g. `02bef8`).     |
| Features      | string    | Hex-encoded feature flags bitmap advertised by the node.         |
| Identity      | identity  | The node's public key, used as its unique identifier.            |
| CustomAlias   | string    | The user-defined alias assigned via the directory service.       |
| LastTimestamp | time      | The timestamp of the last update received for this node.         |
