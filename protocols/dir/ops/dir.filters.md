# dir.filters

Return the names of all registered identity filters. The op streams one `string8` per filter name and terminates with `eos`.

## Returned objects

The operation returns one of:
* A `string8` object for each registered filter name.
* An `eos` object terminating the stream.

## Examples

```shellsession
$ astral-query dir.filters -out json
{"Type":"string8","Object":"local"}
{"Type":"string8","Object":"friends"}
{"Type":"eos","Object":{}}
```
