# player.queue

A snapshot of the play queue. `Version` increases by one on every queue modification (append, remove, move, clear); index-based operations can pass it back to guard against concurrent edits.

## Fields

* Version (uint64) – Monotonically increasing queue version.
* Entries ([]object_id.sha256) – Object IDs of the queued tracks, in play order.

## Example

```json
{
  "Type": "player.queue",
  "Object": {
    "Version": 17,
    "Entries": [
      "data1aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
      "data1bbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbb"
    ]
  }
}
```
