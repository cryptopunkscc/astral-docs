# user.claim

Claim a remote node into the caller's swarm. The caller must be the user
(issuer) of this node's active contract; this node then acts as the user and
invites the target node by calling `user.invite` on it.

Rejected with code `2` if the node has no active contract, or code `3` if the
caller is not the user.

On success the resulting signed contract is indexed in `auth`, stored in
`objects`, and pushed to the rest of the local swarm.

## Arguments

* target (string, required) – Name or identity of the node to invite. Resolved
  via the `dir` module.

## Returned objects

The operation returns one of:
* A `mod.auth.signed_contract` if the target accepted the invitation.
* An `error_message` if the target rejected the invitation or any step failed.

## Examples

```shellsession
$ astral-query user.claim -target laptop -out text
#[mod.auth.signed_contract] ...
```
