# dir.get_alias

Get the alias of an `Identity`.

## Arguments

* id (identity, required) – The identity to get the alias of.

## Returned objects

The operation returns one of:
* An `error_message` object if there was an error.
* A `string8` object containing the alias of the identity.

## Examples

```shellsession
$ astral-query dir.get_alias -id 0282fee8775757cdd8fda8b220195f5b8611312cd145c5a1a3aa55df210e779b2c -out json
{"Type":"string8","Object":"somealias"}
```

```shellsession
$ astral-query dir.get_alias -id 0282fee8775757cdd8fda8b220195f5b8611312cd145c5a1a3aa55df210e779b21 -out json
{"Type":"error_message","Object":"record not found"}
```