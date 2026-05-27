# user.request_invite

Request an invitation from this node into the user's swarm. This node, acting
on behalf of its user, invites the caller (a node identity) by calling
`user.invite` on the caller.

Rejected with code `2` if this node has no active contract.

The `SwarmJoinRequestPolicy` decides whether the caller may join; if it
refuses, the operation responds with the `request declined` error. On success
the signed contract is indexed in `auth`, stored in `objects`, and pushed to
the rest of the local swarm.

## Arguments

This operation takes no arguments.

## Returned objects

The operation returns one of:
* A `mod.auth.signed_contract` if the request was accepted.
* An `error_message` (`request declined`) if the policy refused the caller, or
  another error if any step failed.

## Examples

Used by a node that wants to join a user's swarm to ask the existing nodes for
admission.
