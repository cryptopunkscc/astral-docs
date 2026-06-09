# player.append

Add a track to the play queue. By default the track is appended at the end; with `at`, it is inserted before the entry at that index.

## Arguments

* id (object_id.sha256, required) – Object ID of the track to add.
* at (uint32) – Index to insert the track at. Defaults to the end of the queue.

## Returned objects

The operation returns one of:
* An `error_message` object if the index is out of range or there was an error.
* An `ack` object if the track was added.

## Examples

```shellsession
$ astral-query player.append -id data1aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa -out json
{"Type":"ack","Object":null}
```

```shellsession
$ astral-query player.append -id data1bbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbb -at 0 -out json
{"Type":"ack","Object":null}
```
