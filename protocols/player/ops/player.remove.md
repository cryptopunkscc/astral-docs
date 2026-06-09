# player.remove

Remove an entry from the play queue. Removing the currently playing entry advances playback to the next entry (or stops if it was the last).

## Arguments

* index (uint32, required) – Index of the entry to remove.
* version (uint64) – Expected queue version. If given and the queue has changed since, the operation is rejected.

## Returned objects

The operation returns one of:
* An `error_message` object if the index is out of range, the version does not match, or there was an error.
* An `ack` object if the entry was removed.

## Examples

```shellsession
$ astral-query player.remove -index 3 -version 17 -out json
{"Type":"ack","Object":null}
```
