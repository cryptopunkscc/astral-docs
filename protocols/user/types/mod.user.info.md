# mod.user.info

A snapshot of this node's user configuration: aliases for the node and user
and the active contract under which the node operates.

## Fields

* NodeAlias (string8) – Display name of this node (resolved via `dir`).
* UserAlias (string8) – Display name of the user (resolved via `dir`).
* ContractID (object_id) – ID of the active contract object.
* Contract (mod.auth.signed_contract) – The active contract itself.

## Example

```json
{
  "Type": "mod.user.info",
  "Object": {
    "NodeAlias": "phone",
    "UserAlias": "alice",
    "ContractID": "id....",
    "Contract": { "...": "..." }
  }
}
```
