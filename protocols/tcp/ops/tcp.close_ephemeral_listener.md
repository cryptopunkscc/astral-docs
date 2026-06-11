# tcp.close_ephemeral_listener

Stop an ephemeral TCP listener running on the given port. The operation fails if no ephemeral listener exists on that port.

## Arguments

* port (uint16, required) – TCP port of the listener to close.

## Returned objects

The operation returns one of:
* An `error_message` object if the listener does not exist or cannot be closed.
* An `ack` object if the listener was stopped successfully.

## Examples

```shellsession
$ astral-query tcp.close_ephemeral_listener -port 9000 -out json
{"Type":"ack","Object":null}
```
