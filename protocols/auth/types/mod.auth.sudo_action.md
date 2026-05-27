# mod.auth.sudo_action

A `mod.auth.action` requesting permission for the actor to act as another
identity. The auth module's built-in handler allows this action only when
the actor and target are the same identity; granting it across identities
requires an active `mod.auth.signed_contract` whose permits include
`mod.auth.sudo_action`.

## Fields

This action embeds `mod.auth.action` (Nonce, ActorId) and adds:

* AsID (identity) – Identity the actor is requesting to act as.

## Example

```json
{
  "Type": "mod.auth.sudo_action",
  "Object": {
    "Nonce": "a1b2c3d4e5f60718",
    "ActorId": "0282fee8775757cdd8fda8b220195f5b8611312cd145c5a1a3aa55df210e779b2c",
    "AsID": "03a7c1f5b9d4e62a8f730ce15d2b4a9c11e8d77c3b5f04a6d92e1b8f72c4d3e5a6"
  }
}
```
