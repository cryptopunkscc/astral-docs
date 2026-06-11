# mod.gateway.endpoint

A network address that identifies a target node reachable through a specific gateway node.

## Fields

* GatewayID (identity) – Identity of the gateway node that forwards connections.
* TargetID (identity) – Identity of the destination node behind the gateway.

The text form is `gw:<gatewayID>:<targetID>`; JSON encodes the object as `"<gatewayID>:<targetID>"` (the `gw:` prefix is omitted in the JSON string).

## Example

```json
{
  "Type": "mod.gateway.endpoint",
  "Object": "02bef8840eb35ef2ae3c83c07cb5779278904f99cb4103f71e37cc69931ae5e15f:037f990e61acee8a7697966afd29dd88f3b1f8a7b14d625c4f8742bd952003a590"
}
```
