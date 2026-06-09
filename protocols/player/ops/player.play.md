# player.play

Start or resume playback. Without arguments, resumes the current track if paused, or starts playing the queue from index 0 if stopped. With `index`, jumps to that queue entry and starts playing it from the beginning.

## Arguments

* index (uint32) – Queue index to start playing from.

## Returned objects

The operation returns one of:
* An `error_message` object if the queue is empty or the index is out of range.
* An `ack` object if playback started.

## Examples

```shellsession
$ astral-query player.play -out json
{"Type":"ack","Object":null}
```

```shellsession
$ astral-query player.play -index 4 -out json
{"Type":"ack","Object":null}
```
