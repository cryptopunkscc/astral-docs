# user.adopt

Issue a swarm membership contract for a target node and return the signed result. Rejected with code `2` if the node has no active contract. Rejected with code `3` if the caller is not the active contract's issuer. After indexing, the signed contract is pushed to the local swarm asynchronously and a sync task is scheduled for the new member.

## Arguments

* target (string, required) – Alias or public key of the node to adopt.

## Returned objects

The operation returns one of:
* An `error_message` object if identity resolution, contract issuance, indexing, or storage fails.
* A `mod.auth.signed_contract` object containing the issued membership contract.

## Examples

```shellsession
$ astral-query user.adopt -target laptop -out json
{"Type":"mod.auth.signed_contract","Object":{...}}
```
