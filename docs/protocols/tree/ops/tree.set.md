# tree.set

Set the value at a path. The value is passed as a typed object via the input stream.

## Arguments

* path (string8, required) – The path to write.
* (stream) – A typed object to store at the path.

## Returned objects

The operation returns one of:
* An `error_message` object if there was an error.
* An `ack` object if the value was stored successfully.

## Examples

```shellsession
$ echo '{"Type":"bool","Object":false}' | astral-query tree.set -path /mod/tcp/settings/listen -in json -out json
{"Type":"ack","Object":null}
```

```shellsession
$ echo '{"Type":"string8","Object":"hello"}' | astral-query tree.set -path /tmp/mykey -in json -out json
{"Type":"ack","Object":null}
```
