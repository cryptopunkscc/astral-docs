# apphost.cancel

Cancel an en-route query by nonce.

## Arguments

* id (nonce64, required) – Nonce of the query to cancel.
* cause (string) – Optional cause attached to the cancellation as an error.

## Returned objects

The operation returns one of:
* An `error_message` object if the query was not found.
* An `ack` object if the query was cancelled.

## Examples

```shellsession
$ astral-query apphost.cancel -id a3f1c2d4e5b6f708 -cause "user aborted" -out text
#[ack]
```
