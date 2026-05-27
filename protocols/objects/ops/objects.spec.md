# objects.spec

Describe the fields of registered astral struct types — useful for tooling that builds queries or forms dynamically.

## Arguments

* type (string8) – If set, only the spec for this type is returned. Otherwise specs for every registered struct type are streamed (sorted by name).
* in (string8) – Input format.
* out (string8) – Output format.

## Returned objects

The operation returns a stream of `objects.type_spec` objects followed by an `eos` object. Types with no inspectable fields (e.g. opaque or non-struct) are skipped.

## Examples

```shellsession
$ astral-query objects.spec -type mod.objects.repository_info -out json
{"Type":"objects.type_spec","Object":{"Name":"mod.objects.repository_info","Fields":[{"Name":"Name","Type":"string8","Required":true},{"Name":"Label","Type":"string8","Required":true},{"Name":"Free","Type":"int64","Required":true}]}}
{"Type":"eos","Object":null}
```

```shellsession
$ astral-query objects.spec -type mod.objects.probe -out json
{"Type":"objects.type_spec","Object":{"Name":"mod.objects.probe","Fields":[{"Name":"Type","Type":"string8","Required":true},{"Name":"Repo","Type":"string8","Required":true},{"Name":"Mime","Type":"string8","Required":true},{"Name":"Time","Type":"duration","Required":true}]}}
{"Type":"eos","Object":null}
```
