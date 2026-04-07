# lna.node

A structure containing information about a Lightning Network node.

## Fields

* Alias (string) – The node's self-reported alias from the Lightning Network.
* Color (string) – The node's advertised color as a hex string (e.g. `02bef8`).
* Features (string) – Hex-encoded feature flags bitmap advertised by the node.
* Identity (identity) – The node's public key, used as its unique identifier.
* CustomAlias (string) – The user-defined alias assigned via the directory service.
* LastTimestamp (time) – The timestamp of the last update received for this node.

## Example

```json
{
  "Type": "lna.node",
  "Object": {
    "Alias": "void0",
    "Color": "02bef8",
    "CustomAlias": "cln",
    "Features": "808898880a8a59a1",
    "Identity": "02bef8840eb35ef2ae3c83c07cb5779278904f99cb4103f71e37cc69931ae5e15f",
    "LastTimestamp": 1774881178
  }
}
```
