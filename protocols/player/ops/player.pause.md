# player.pause

Pause playback. The operation is idempotent – pausing an already paused or stopped player succeeds without effect.

## Arguments

None.

## Returned objects

The operation returns one of:
* An `error_message` object if there was an error.
* An `ack` object if the player is paused.

## Examples

```shellsession
$ astral-query player.pause -out json
{"Type":"ack","Object":null}
```
