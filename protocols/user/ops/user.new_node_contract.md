# user.new_node_contract

Build an unsigned `mod.auth.contract` that grants
`mod.user.swarm_membership_action` from a user identity to a node identity for a
given duration. Used by tooling that wants to assemble a contract before
asking the issuer and subject to sign it.

## Arguments

* user (string, optional) – Name or identity of the issuer (user). Defaults to
  this node's user (from the active contract).
* node (string, optional) – Name or identity of the subject (node). Defaults
  to the local node.
* duration (string, optional) – Go-style duration (e.g. `8760h`). Defaults to
  one year.

## Returned objects

The operation returns one of:
* A `mod.auth.contract` ready to be signed.
* An `error_message` if either identity could not be resolved, the duration
  failed to parse, or contract construction failed.

## Examples

```shellsession
$ astral-query user.new_node_contract -user alice -node laptop -duration 720h -out text
#[mod.auth.contract] ...
```
