# dir.set_alias

Set or remove an alias for an identity.

## Arguments

* id (identity, required) – The identity to set the alias for
* alias (string8) – The alias to set. No alias to remove.

## Returned objects

The operation returns one of:
* An `error_message` object if there was an error.
* An `ack` object if the operation was successful.

## Examples

```shellsession
$ astral-query dir.set_alias -id 0282fee8775757cdd8fda8b220195f5b8611312cd145c5a1a3aa55df210e779b2c -alias somealias -out text
#[ack] 
```
