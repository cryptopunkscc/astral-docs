# mod.users.created_user_info

The result returned when a new user account is created, bundling the identity, alias, keys, contract, and access token in a single object.

## Fields

* ID (identity) – The newly created user identity.
* Alias (string8) – The display name assigned to the new user.
* KeyID (object_id) – ID of the private-key object stored for the user.
* ContractID (object_id) – ID of the node contract issued for the user.
* Contract (mod.auth.signed_contract) – The co-signed node contract itself.
* AccessToken (string8) – A short-lived token the caller can present to authenticate as the new user.

## Example

```json
{
  "Type": "mod.users.created_user_info",
  "Object": {
    "ID": "0282fee8775757cdd8fda8b220195f5b8611312cd145c5a1a3aa55df210e779b2c",
    "Alias": "alice",
    "KeyID": "data1ybndrfg8ejkmcpqxot1uwisza345h769ybndrfg8ejkmcpqxot1uwisza34",
    "ContractID": "data1ybndrfg8ejkmcpqxot1uwisza345h769ybndrfg8ejkmcpqxot1uwisza35",
    "Contract": { "...": "..." },
    "AccessToken": "tok_xxxxxxxxxxxxxxxx"
  }
}
```
