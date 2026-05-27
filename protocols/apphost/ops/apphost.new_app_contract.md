# apphost.new_app_contract

Create an unsigned app contract granting the local node relay-for permission
on behalf of the given app identity.

## Arguments

* id (identity, required) – The app identity that will issue the contract.
* duration (duration) – Validity period of the contract. Defaults to 1 year.

## Returned objects

The operation returns one of:
* An `error_message` object if there was an error.
* A `mod.auth.contract` object containing the unsigned contract.

## Examples

```shellsession
$ astral-query apphost.new_app_contract -id 0282fee8775757cdd8fda8b220195f5b8611312cd145c5a1a3aa55df210e779b2c -out json
{"Type":"mod.auth.contract","Object":{"Issuer":"0282fee8775757cdd8fda8b220195f5b8611312cd145c5a1a3aa55df210e779b2c","Subject":"026165850492521f4ac8abd9bd8088123446d126f648ca35e60f88177dc149ceb2","Permits":[{"Action":"mod.nodes.relay_for_action"}],"ExpiresAt":"2027-05-27T12:00:00+02:00"}}
```
