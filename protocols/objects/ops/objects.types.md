# objects.types

List every astral type name registered with the default blueprints (sorted alphabetically).

## Arguments

* out (string8) – Output format.

## Returned objects

The operation returns a stream of `string8` objects, one per type name. The stream is not terminated by an `eos`; it ends when the writer closes.

## Examples

```shellsession
$ astral-query objects.types -out json
{"Type":"string8","Object":"ack"}
{"Type":"string8","Object":"blob"}
{"Type":"string8","Object":"bool"}
{"Type":"string8","Object":"eos"}
{"Type":"string8","Object":"identity"}
{"Type":"string8","Object":"mod.objects.probe"}
{"Type":"string8","Object":"object_id.sha256"}
{"Type":"string8","Object":"objects.search_query"}
{"Type":"string8","Object":"string8"}
```
