# mod.nodes.link_closed_event

Emitted when a link to a remote identity is closed.

## Fields

* RemoteIdentity (identity) – Identity of the other party on the closed link.
* Forced (bool) – True if the link was closed forcibly (e.g. via `nodes.close_link` or an error) rather than gracefully.
* LinkCount (int8) – Number of remaining links to the same remote identity after this close.

## Example

```json
{
  "Type": "mod.nodes.link_closed_event",
  "Object": {
    "RemoteIdentity": "037f990e61acee8a7697966afd29dd88f3b1f8a7b14d625c4f8742bd952003a590",
    "Forced": false,
    "LinkCount": 0
  }
}
```
