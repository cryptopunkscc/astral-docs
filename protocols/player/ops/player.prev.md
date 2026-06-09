# player.prev

Skip to the previous queue entry. If the current track is the first entry, it restarts from the beginning.

## Arguments

None.

## Returned objects

The operation returns one of:
* An `error_message` object if no track is loaded or there was an error.
* An `ack` object if the skip succeeded.

## Examples

```shellsession
$ astral-query player.prev -out json
{"Type":"ack","Object":null}
```
