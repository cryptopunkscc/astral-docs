# player.clear

Remove all entries from the play queue and stop playback.

## Arguments

None.

## Returned objects

The operation returns one of:
* An `error_message` object if there was an error.
* An `ack` object if the queue was cleared.

## Examples

```shellsession
$ astral-query player.clear -out json
{"Type":"ack","Object":null}
```
