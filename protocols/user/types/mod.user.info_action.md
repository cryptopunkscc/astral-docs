# mod.user.info_action

A [`mod.auth.action`](../../auth/types/mod.auth.action.md) requesting permission
for the actor to read the active contract's metadata. It is the typed action
gating the `user.info` op: an active contract whose permits include this action
authorizes the read. When evaluating the request the auth module matches a
permit to the action by object type.

## Fields

* Action ([`mod.auth.action`](../../auth/types/mod.auth.action.md)) – The embedded base action carrying the Nonce and ActorID.

This action carries no extra fields of its own beyond the embedded
`mod.auth.action`.

## Example

```json
{
  "Type": "mod.user.info_action",
  "Object": {
    "Action": {
      "Nonce": "a1b2c3d4e5f60718",
      "ActorID": "0282fee8775757cdd8fda8b220195f5b8611312cd145c5a1a3aa55df210e779b2c"
    }
  }
}
```
