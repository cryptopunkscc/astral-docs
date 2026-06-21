# user.expel

Permanently ban a target node from the swarm and return the signed expulsion. Rejected with code `2` if the node has no active contract. Rejected with code `3` if the caller is not the active contract's issuer. The ban is identity-level and irreversible.

## Arguments

* target (string, required) – Alias or public key of the node to expel.

## Returned objects

The operation returns one of:
* An `error_message` object if identity resolution or expulsion fails.
* A `mod.user.signed_expulsion` object containing the issued ban.

## Examples

```shellsession
$ astral-query user.expel -target phone -out json
{"Type":"mod.user.signed_expulsion","Object":{...}}
```
