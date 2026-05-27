# apphost.unhold_object

Release the calling app's hold on an object. Local-only — queries from the
network are rejected.

## Arguments

* id (object_id.sha256, required) – The object whose hold should be released.

## Returned objects

The operation returns one of:
* An `error_message` object if the caller is missing an identity, the object id is missing, or the database call failed.
* An `ack` object if the hold was released.

## Examples

```shellsession
$ astral-query apphost.unhold_object -id sha256:3b1f5d8c... -out text
#[ack]
```
