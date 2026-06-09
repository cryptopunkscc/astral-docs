# player.move

Move a queue entry to a new position. Moving the currently playing entry does not interrupt playback – the state's `Index` follows the entry.

## Arguments

* from (uint32, required) – Index of the entry to move.
* to (uint32, required) – Index to move the entry to.
* version (uint64) – Expected queue version. If given and the queue has changed since, the operation is rejected.

## Returned objects

The operation returns one of:
* An `error_message` object if an index is out of range, the version does not match, or there was an error.
* An `ack` object if the entry was moved.

## Examples

```shellsession
$ astral-query player.move -from 5 -to 0 -version 17 -out json
{"Type":"ack","Object":null}
```
