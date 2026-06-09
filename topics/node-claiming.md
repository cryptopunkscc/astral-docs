# Node Claiming

Claiming brings a previously unclaimed [`Node`](../core-primitives/node.md) into a [`User`](../core-primitives/user.md)'s swarm by
installing a fresh `mod.user.swarm_access_action` contract on it. The
initiator already holds an active contract; the target does not. See
[Node Setup](node-setup.md) for how the initiator obtains its first active
contract.

## Claim

From the initiator, acting as the `User`:

```shellsession
$ astral-query user.claim -target <target-node-id-or-alias>
```

That is the entire flow. The initiator builds the contract, signs as
issuer, calls [`user.invite`](../protocols/user/ops/user.invite.md) on the
target, receives the subject signature, and returns the resulting
`mod.auth.signed_contract`. The target verifies, indexes, stores it, and
sets it as its active contract.

Preconditions:
* The initiator has an active contract; otherwise
  [`user.claim`](../protocols/user/ops/user.claim.md) rejects with code `2`.
* The caller is the `User` (issuer of that contract); otherwise rejected
  with code `3`.
* The target has no active contract; otherwise
  [`user.invite`](../protocols/user/ops/user.invite.md) rejects with
  code `2`.
* The target's `SwarmInvitePolicy` accepts the caller (default: accept
  all).

## Reachability

`user.claim` opens a query on the target, which requires that the two
nodes can establish a `nodes` link. Nothing in the claim flow itself sets
up transport — endpoints must already be known or discoverable.

* **Same local swarm.** The `nearby` module announces nodes on the local
  network; no manual endpoint setup is required.
* **Remote nodes.** The initiator must learn at least one usable endpoint
  for the target before the claim query can be routed. Register endpoints
  with
  [`nodes.add_endpoint`](../protocols/nodes/ops/nodes.add_endpoint.md);
  the endpoint format is `<network>:<address>` (e.g. `tcp:1.2.3.4:1791`,
  `tor:abcdefghijklmnop.onion:1791`).

On the initiator, teach it where the target lives:

```shellsession
$ astral-query nodes.add_endpoint \
    -id <target-node-id> \
    -endpoint tcp:1.2.3.4:1791
```

On the target, teach it where the initiator lives so siblings can link
back after the contract is installed:

```shellsession
$ astral-query nodes.add_endpoint \
    -id <initiator-node-id> \
    -endpoint tcp:5.6.7.8:1791
```

Known endpoints can be inspected with
[`nodes.resolve_endpoints`](../protocols/nodes/ops/nodes.resolve_endpoints.md).

## After Claiming

* The target's `mod.user.Identity()` now returns the `User` identity.
* The `auth` index lists the new `mod.auth.signed_contract`; it shows up
  in [`user.list_siblings`](../protocols/user/ops/user.list_siblings.md)
  and [`user.swarm_status`](../protocols/user/ops/user.swarm_status.md).
* The target broadcasts presence (`nearby.Broadcast`) and starts
  `runSiblingLinker`; on the next sibling link the active contract is
  pushed so existing nodes re-index it.
* Confirm on either side with
  [`user.info`](../protocols/user/ops/user.info.md).

## Reverse Flow

When the unclaimed node initiates instead of the user, it sends
[`user.request_invite`](../protocols/user/ops/user.request_invite.md) to
any node already in the swarm. The contacted node consults its
`SwarmJoinRequestPolicy` (default: accept all) and runs the same invite
path with the requester as subject.
