# dir.resolve

## Description

Resolve an `identity` of a given name using any supported resolution 
mechanism. By default public keys and aliases are supported, but modules can add more mechanims.

## Arguments

| name | type    | description              |
| ---- | ------- | ------------------------ |
| name | string8 | The name to be resolved. |

## Return values

On success the call returns a single `identity` object.

On error it returns nothing.

## Examples

```shellsession
$ astral-query dir.resolve -name somealias -out json
{"Type":"identity","Object":"0282fee8775757cdd8fda8b220195f5b8611312cd145c5a1a3aa55df210e779b2c"}
```