# objects.register_blueprint

Register runtime `astral.Blueprint` descriptors (struct kind or alias kind) with `DefaultBlueprints`. The op reads blueprints from the input stream until `eos` or EOF, registers each, and sends the resulting `object_id.sha256` or an `error_message` per input. A final `eos` object is sent before the channel closes.

## Arguments

* in (string8) – Input format.
* out (string8) – Output format.
* (stream) – `astral.Blueprint` objects to register, terminated by an `eos` object.

## Returned objects

The operation returns one of:
* An `error_message` object if a non-blueprint object is received or registration fails.
* An `object_id.sha256` object for each successfully registered blueprint.
* An `eos` object terminating the stream.

## Examples

```shellsession
$ echo '{"Type":"astral.Blueprint","Object":{"Kind":"struct","Name":"example.thing","Fields":[]}}
{"Type":"eos","Object":null}' | astral-query objects.register_blueprint -in json -out json
{"Type":"object_id.sha256","Object":"data1aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"}
{"Type":"eos","Object":null}
```
