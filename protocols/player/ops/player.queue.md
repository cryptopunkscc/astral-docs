# player.queue

Get the current play queue.

## Arguments

* follow (bool) – If true, stream a new queue snapshot on every queue change (the operation stays open).

## Returned objects

The operation returns one of:
* An `error_message` object if there was an error.
* A `player.queue` object, followed by an `eos` object (or a stream of queue snapshots if `follow` is true).

## Examples

```shellsession
$ astral-query player.queue -out json
{"Type":"player.queue","Object":{"Version":17,"Entries":["data1aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa","data1bbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbb"]}}
{"Type":"eos","Object":null}
```
