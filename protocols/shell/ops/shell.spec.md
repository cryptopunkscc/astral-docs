# shell.spec

Stream the operation specifications for all ops registered under the shell module, sorted by name. Each spec describes one op's name and parameter list. Optionally filter to a single op by name.

## Arguments

* op (string) – If set, return only the spec for the op with this exact name. Defaults to all ops.
* out (string8) – Output format.

## Returned objects

The operation returns a stream of `routing.op_spec` objects (one per matching op) followed by an `eos` object.

## Examples

```shellsession
$ astral-query shell.spec -out json
{"Type":"routing.op_spec","Object":{"Name":"shell.shell","Parameters":[{"Name":"as","Type":"string8","Required":false}]}}
{"Type":"routing.op_spec","Object":{"Name":"shell.spec","Parameters":[{"Name":"op","Type":"string","Required":false},{"Name":"out","Type":"string","Required":false}]}}
{"Type":"eos","Object":null}
```
