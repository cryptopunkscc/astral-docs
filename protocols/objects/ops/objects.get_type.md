# objects.get_type

Return the astral type name of an object, reading just enough bytes to parse the stamp and type header.

## Arguments

* id (object_id.sha256, required) – The id to inspect.
* out (string8) – Output format.

## Returned objects

The operation returns one of:
* An `error_message` object with `unknown type` if the object cannot be read, has no astral stamp, or the type cannot be parsed.
* A `string8` object containing the type name.

## Examples

```shellsession
$ astral-query objects.get_type -id data1aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa -out json
{"Type":"string8","Object":"string8"}
```
