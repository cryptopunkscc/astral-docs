# apphost.whoami

Return the identity of the caller as authenticated by the host.

## Arguments

This operation takes no arguments.

## Returned objects

The operation returns an `identity` object — the caller's identity.

## Examples

```shellsession
$ astral-query apphost.whoami -out json
{"Type":"identity","Object":"0282fee8775757cdd8fda8b220195f5b8611312cd145c5a1a3aa55df210e779b2c"}
```
