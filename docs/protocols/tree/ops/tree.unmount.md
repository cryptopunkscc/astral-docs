# tree.unmount

Unmount a previously mounted remote subtree from a local path.

## Arguments

* path (string8, required) – The local path to unmount.

## Returned objects

The operation returns one of:
* An `error_message` object if the path is not mounted or there was an error.
* An `ack` object if the unmount was successful.

## Examples

```shellsession
$ astral-query tree.unmount -path /remote/peer -out json
{"Type":"ack","Object":null}
```
