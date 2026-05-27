# mod.nodes.link_pressure_event

Emitted when an active link transitions into a back-pressure condition (sender outpacing receiver).

## Fields

* RemoteIdentity (identity) – Identity of the other party on the pressured link.
* LinkID (nonce64) – Local id of the affected link.

## Example

```json
{
  "Type": "mod.nodes.link_pressure_event",
  "Object": {
    "RemoteIdentity": "037f990e61acee8a7697966afd29dd88f3b1f8a7b14d625c4f8742bd952003a590",
    "LinkID": "7c1a93b50f2e4d18"
  }
}
```
