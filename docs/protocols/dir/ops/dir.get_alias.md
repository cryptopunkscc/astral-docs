# dir.get_alias

Get the (locally set) alias of an `identity`.

## Description

This method gets the (locally set) alias for the provided `identity`.

## Arguments

| name | type     | description                        |
| ---- | -------- | ---------------------------------- |
| id   | identity | The identitty to get the alias for |

## Return values

The method returns a single `string8` object containing the alias for the identity.

## Examples

```shellsession
$ astral-query dir.get_alias -id 0282fee8775757cdd8fda8b220195f5b8611312cd145c5a1a3aa55df210e779b2c -out text
#[string8] somealias
```
