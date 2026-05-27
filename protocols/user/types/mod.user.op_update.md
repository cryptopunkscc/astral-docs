# mod.user.op_update

One entry in the asset operation log streamed by `user.sync_assets`. Each
entry is either an addition or a removal (tombstone) of an object from the
user's asset list. Entries are ordered by an internal monotonically increasing
height; callers track that height to fetch only new entries on subsequent
calls.

## Fields

* Nonce (nonce) – Unique identifier of this log entry.
* ObjectID (object_id) – ID of the asset object.
* Removed (bool) – `true` if the entry is a tombstone, `false` for an
  addition.

## Example

```json
{
  "Type": "mod.user.op_update",
  "Object": {
    "Nonce": "...",
    "ObjectID": "id1....",
    "Removed": false
  }
}
```
