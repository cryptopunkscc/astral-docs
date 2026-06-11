# mod.gateway.socket

A raw connection point at the gateway; the recipient opens a raw exonet connection to `Endpoint` and sends `Nonce` as the first bytes to identify itself to the gateway.

## Fields

* Endpoint (object) – The `exonet.Endpoint` to dial (typically a `mod.gateway.endpoint`).
* Nonce (nonce64) – One-time token the recipient sends after connecting to claim the reserved slot.

## Example

```json
{
  "Type": "mod.gateway.socket",
  "Object": {
    "Endpoint": {
      "Type": "mod.gateway.endpoint",
      "Object": "02bef8840eb35ef2ae3c83c07cb5779278904f99cb4103f71e37cc69931ae5e15f:037f990e61acee8a7697966afd29dd88f3b1f8a7b14d625c4f8742bd952003a590"
    },
    "Nonce": "3f7a1c2e9b0d4e5f"
  }
}
```
