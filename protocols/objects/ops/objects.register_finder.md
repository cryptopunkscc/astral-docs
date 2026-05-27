# objects.register_finder

Register the caller as an external finder. The module proxies `objects.find` calls back to the caller's identity for the lifetime of the registration. Network-originated queries are rejected.

## Arguments

* in (string8) – Input format.
* out (string8) – Output format.

## Returned objects

The operation returns one of:
* An `error_message` object if the caller identity is missing/zero, the caller is the node itself, or the finder cannot be added.
* An `ack` object once the external finder is registered.

## Examples

```shellsession
$ astral-query objects.register_finder -out json
{"Type":"ack","Object":null}
```
