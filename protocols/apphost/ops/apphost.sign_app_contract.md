# apphost.sign_app_contract

Sign an app contract supplied by the caller. The node co-signs the contract,
indexes it, stores it, and pushes the signed contract to the local user swarm.
The caller sends a `mod.auth.contract` object on the channel and receives the
signed result.

## Arguments

This operation takes no arguments.

## Returned objects

The operation returns one of:
* An `error_message` object if signing, indexing, or storage failed.
* A `mod.auth.signed_contract` object containing the signed contract.

## Examples

```shellsession
$ astral-query apphost.sign_app_contract -in json -out json
{"Type":"mod.auth.contract","Object":{"Issuer":"0282fee8775757cdd8fda8b220195f5b8611312cd145c5a1a3aa55df210e779b2c","Subject":"026165850492521f4ac8abd9bd8088123446d126f648ca35e60f88177dc149ceb2","Permits":[{"Action":"mod.nodes.relay_for_action"}],"ExpiresAt":"2027-05-27T12:00:00+02:00"}}
{"Type":"mod.auth.signed_contract","Object":{"Contract":{"Issuer":"0282fee8775757cdd8fda8b220195f5b8611312cd145c5a1a3aa55df210e779b2c","Subject":"026165850492521f4ac8abd9bd8088123446d126f648ca35e60f88177dc149ceb2","Permits":[{"Action":"mod.nodes.relay_for_action"}],"ExpiresAt":"2027-05-27T12:00:00+02:00"},"Signatures":["..."]}}
```
