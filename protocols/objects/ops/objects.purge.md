# objects.purge

Delete objects from a repository in oldest-read-first order, skipping any object that is currently held by a registered holder.

## Arguments

* repo (string8, required) – Repository to purge.
* zone (zone) – Zone filter for the delete context. Defaults to all zones.
* out (string8) – Output format.

## Returned objects

The operation returns one of:
* An `error_message` object if the repository is not found or the purge fails mid-stream (sent after any ids already purged).
* A stream of `object_id.sha256` objects, one per purged object, followed by an `eos` object.

## Examples

```shellsession
$ astral-query objects.purge -repo local -out json
{"Type":"object_id.sha256","Object":"data1aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"}
{"Type":"object_id.sha256","Object":"data1bbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbb"}
{"Type":"eos","Object":null}
```
