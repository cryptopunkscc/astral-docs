# mod.user.expel_action

A [`mod.auth.action`](../../auth/types/mod.auth.action.md) requesting permission
for the actor to expel a node from the user's swarm. It is the typed action
gating the `user.expel` op: an active contract whose permits include this action
authorizes the expulsion. When evaluating the request the auth module matches a
permit to the action by object type.

## Fields

* Action ([`mod.auth.action`](../../auth/types/mod.auth.action.md)) – The embedded base action carrying the Nonce and ActorID.
* Subject (identity) – Identity of the node being expelled from the swarm.

## Example

```json
{
  "Type": "mod.user.expel_action",
  "Object": {
    "Action": {
      "Nonce": "a1b2c3d4e5f60718",
      "ActorID": "0282fee8775757cdd8fda8b220195f5b8611312cd145c5a1a3aa55df210e779b2c"
    },
    "Subject": "037f990e61acee8a7697966afd29dd88f3b1f8a7b14d625c4f8742bd952003a590"
  }
}
```
