# apphost.install_app

Install a local app by creating, signing, indexing, and storing an app
contract for it, then recording it in the local app registry. Local-only —
queries from the network are rejected.

## Arguments

* id (identity, required) – The app identity to install.
* duration (duration) – Validity period of the contract. Defaults to 1 year.

## Returned objects

The operation returns one of:
* An `error_message` object if any step failed.
* A `mod.auth.signed_contract` object containing the installed contract.

## Examples

```shellsession
$ astral-query apphost.install_app -id 0282fee8775757cdd8fda8b220195f5b8611312cd145c5a1a3aa55df210e779b2c -out json
{"Type":"mod.auth.signed_contract","Object":{"Contract":{"Issuer":"0282fee8775757cdd8fda8b220195f5b8611312cd145c5a1a3aa55df210e779b2c","Subject":"026165850492521f4ac8abd9bd8088123446d126f648ca35e60f88177dc149ceb2","Permits":[{"Action":"mod.nodes.relay_for_action"}],"ExpiresAt":"2027-05-27T12:00:00+02:00"},"Signatures":["..."]}}
```
