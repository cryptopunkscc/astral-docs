# dir.resolve

Resolve an `identity` from the string. The string can be:
* The pubkey hex string of the `identity`
* The alias of the `identity`

## Arguments

* name (string8, required) – The name to be resolved.

## Returned objects

The operation returns one of:
* An `error_message` object if there was an error.
* An `identity` object if the name was resolved.

## Examples

```shellsession
$ astral-query dir.resolve -name somealias -out json
{"Type":"identity",Object":"0282fee8775757cdd8fda8b220195f5b8611312cd145c5a1a3aa55df210e779b2c"}
```