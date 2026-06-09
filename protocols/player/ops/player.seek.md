# player.seek

Seek within the current track. Positions beyond the track duration are clamped to the end of the track.

## Arguments

* position (uint64, required) – Target position in milliseconds.

## Returned objects

The operation returns one of:
* An `error_message` object if no track is loaded or there was an error.
* An `ack` object if the seek succeeded.

## Examples

```shellsession
$ astral-query player.seek -position 60000 -out json
{"Type":"ack","Object":null}
```
