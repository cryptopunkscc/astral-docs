# mod.nodes.link_created_event

Emitted when a new link to a remote identity becomes active.

## Fields

* RemoteIdentity (identity) – Identity of the other party on the new link.
* LinkID (nonce64) – Local id of the new link.
* LinkCount (int) – Total number of links to the same remote identity after this addition.

## Example

```json
{
  "Type": "mod.nodes.link_created_event",
  "Object": {
    "RemoteIdentity": "037f990e61acee8a7697966afd29dd88f3b1f8a7b14d625c4f8742bd952003a590",
    "LinkID": "7c1a93b50f2e4d18",
    "LinkCount": 1
  }
}
```
