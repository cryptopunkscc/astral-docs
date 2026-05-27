# apphost.hold_object

Place a hold on an object on behalf of the calling app, preventing it from
being purged for the hold's duration. Local-only — queries from the network
are rejected.

## Arguments

* id (object_id.sha256, required) – The object to hold.
* duration (duration) – How long to hold the object. No duration means an indefinite hold.

## Returned objects

The operation returns one of:
* An `error_message` object if the caller is missing an identity, the object id is missing, or the database call failed.
* An `ack` object if the hold was placed.

## Examples

```shellsession
$ astral-query apphost.hold_object -id sha256:3b1f5d8c... -duration 24h -out text
#[ack]
```
