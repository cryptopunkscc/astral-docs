# mod.nearby.public_profile

The publicly broadcast identity and alias of a nearby node.

## Fields

* NodeID (identity) – The node's identity (secp256k1 public key).
* NodeAlias (string8) – The human-readable alias of the node.

## Example

```json
{
  "Type": "mod.nearby.public_profile",
  "Object": {
    "NodeID": "02bef8840eb35ef2ae3c83c07cb5779278904f99cb4103f71e37cc69931ae5e15f",
    "NodeAlias": "alice"
  }
}
```
