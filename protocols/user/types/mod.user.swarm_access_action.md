# mod.user.swarm_access_action

The `mod.auth.action` used in node contracts to grant a node membership in a
user's swarm. A signed contract whose permits include this action makes the
subject (a node) a member of the issuer's (user's) swarm; the `user` module
treats such a contract as a "node contract".

## Fields

This action carries no extra fields beyond the embedded `mod.auth.action`.

## Example

A node contract is a `mod.auth.contract` with a single permit whose `Action`
field equals `mod.user.swarm_access_action`.

```json
{
  "Type": "mod.auth.contract",
  "Object": {
    "Issuer": "...user identity...",
    "Subject": "...node identity...",
    "Permits": [
      { "Action": "mod.user.swarm_access_action" }
    ],
    "ExpiresAt": "2027-05-27T12:00:00+02:00"
  }
}
```
