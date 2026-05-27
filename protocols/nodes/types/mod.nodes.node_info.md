# mod.nodes.node_info

A compact descriptor of a node: its alias, identity, and a list of known endpoints. Text-encodes as a base62 string (the `node1` info format).

## Fields

* Alias (string8) – Self-reported alias for the node.
* Identity (identity) – The node's public key.
* Endpoints ([]object) – List of `exonet.Endpoint` objects. On the wire each entry is preceded by a `uint8` type tag (`0` = tcp, `1` = tor, `2` = gateway, `3` = utp). The list length is encoded as a `uint8` and therefore capped at 255.

## Example

```json
{
  "Type": "mod.nodes.node_info",
  "Object": {
    "Alias": "void0",
    "Identity": "02bef8840eb35ef2ae3c83c07cb5779278904f99cb4103f71e37cc69931ae5e15f",
    "Endpoints": [
      { "Type": "tcp.endpoint", "Object": "1.2.3.4:1791" },
      { "Type": "tor.endpoint", "Object": "abcdefghijklmnop.onion:1791" }
    ]
  }
}
```
