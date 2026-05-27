# user.invite

Accept an invitation from a user to join their swarm. The local node is the
subject of the contract being signed.

The node must not already have an active contract — rejected with code `2`
otherwise. The caller sends a `mod.auth.contract` and then a `mod.crypto.signature`
(the issuer signature) over the same channel; the node validates the contract,
asks its `SwarmInvitePolicy` to approve the caller, signs as subject, sends
back its `mod.crypto.signature`, indexes and stores the signed contract, and
sets it as the active contract.

The contract must satisfy:
* The `Subject` is the local node's identity.
* `ExpiresAt` is at least one hour in the future.
* The issuer signature verifies.

## Arguments

This operation takes no arguments.

## Channel flow

1. Caller sends `mod.auth.contract`.
2. Caller sends `mod.crypto.signature` (issuer signature).
3. Operation responds with either:
   * A `mod.crypto.signature` (the subject signature).
   * An `error_message` — including `mod.auth.invalid_contract` if the contract
     fails validation, or `invitation declined` if the swarm policy refuses
     the caller.

## Examples

Used internally by `user.claim` and `user.request_invite`; not normally
issued from the command line.
