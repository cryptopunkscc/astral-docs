# dir.set_alias

Set an alias for an identity.

## Arguments

| name  | type     | description                        |
| ----- | -------- | ---------------------------------- |
| id    | identity | The identitty to set the alias for |
| alias | string8  | The alias                          |

## Return values

The method returns a single `ack` object on success or an `error_message` on error.

## Examples

```shellsession
$ astral-query dir.set_alias -id 0282fee8775757cdd8fda8b220195f5b8611312cd145c5a1a3aa55df210e779b2c -alias somealias -out text
#[ack] 
```
