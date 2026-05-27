# objects.new

Construct a zero-valued instance of a registered astral type.

## Arguments

* type (string8, required) – The astral type name to instantiate (e.g. `string8`, `mod.objects.probe`).
* in (string8) – Input format.
* out (string8) – Output format.

## Returned objects

The operation returns one of:
* A `nil` object if the type name is not registered.
* A zero-valued instance of the requested type.

## Examples

```shellsession
$ astral-query objects.new -type bool -out json
{"Type":"bool","Object":false}
```

```shellsession
$ astral-query objects.new -type nonexistent.type -out json
{"Type":"nil","Object":null}
```
