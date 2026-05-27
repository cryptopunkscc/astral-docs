# mod.nodes.session_info

Describes a single open multiplexed session, identified by a nonce and carried by a specific link.

## Fields

* ID (nonce64) – Session nonce, unique across the node.
* LinkID (nonce64) – Local id of the link currently carrying this session.
* RemoteIdentity (identity) – The remote end's identity.
* Outbound (bool) – True if the session was initiated by this node.
* Query (string16) – The original query string that opened the session.
* Bytes (uint64) – Total bytes transferred over the session so far.
* Age (duration) – Nanoseconds since the session was created.

## Example

```json
{
  "Type": "mod.nodes.session_info",
  "Object": {
    "ID": "a1b2c3d4e5f60718",
    "LinkID": "7c1a93b50f2e4d18",
    "RemoteIdentity": "037f990e61acee8a7697966afd29dd88f3b1f8a7b14d625c4f8742bd952003a590",
    "Outbound": true,
    "Query": "objects.get",
    "Bytes": 4096,
    "Age": 12000000000
  }
}
```
