# gateway.node_unregister

Unregister the caller from the gateway. All idle connections and pending connectors associated with the caller's identity are closed.

## Arguments

No arguments.

## Returned objects

The operation returns one of:
* An `error_message` object if the caller is not currently registered.
* An `ack` object on success.

## Examples

```shellsession
$ astral-query gateway.node_unregister -out json
{"Type":"ack","Object":{}}
```
