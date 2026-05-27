# objects.create

Create a new object by streaming raw payload chunks into a repository.

## Arguments

* alloc (uint64) – Pre-allocation hint in bytes for the underlying writer.
* repo (string8) – Repository name. Defaults to the write-default repository.
* in (string8) – Input format for streamed payload objects.
* out (string8) – Output format.
* (stream) – A stream of `blob` chunks terminated by a `mod.objects.commit_msg` object. Closing before commit discards the data.

## Returned objects

The operation returns one of:
* An `error_message` object if the repository is not found or write/commit fails.
* An `ack` object acknowledging the open writer, then either an `object_id.sha256` (on successful commit) or an `error_message` (on commit failure).

## Examples

```shellsession
$ astral-query objects.create -repo local -out json
{"Type":"ack","Object":null}
{"Type":"object_id.sha256","Object":"data1aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"}
```
