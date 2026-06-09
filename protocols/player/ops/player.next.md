# player.next

Skip to the next queue entry. If the current track is the last entry, playback stops.

## Arguments

None.

## Returned objects

The operation returns one of:
* An `error_message` object if no track is loaded or there was an error.
* An `ack` object if the skip succeeded.

## Examples

```shellsession
$ astral-query player.next -out json
{"Type":"ack","Object":null}
```
