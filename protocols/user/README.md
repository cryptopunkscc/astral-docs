# user

The `user` protocol manages the identity of the user that owns this node, the
swarm of nodes operating under that user, and the user's asset list.

A node joins a user's swarm by holding an active `mod.user.swarm_membership_action`
contract issued by that user. Once a node has an active contract it can serve
information about the user (`user.info`), enumerate the swarm
(`user.swarm_status`, `user.list_siblings`), maintain a synchronised list of
user assets (`user.assets`, `user.add_asset`, `user.remove_asset`,
`user.sync_assets`, `user.sync_with`).

Swarm membership is managed through contract ops: a user adopts a node with
`user.adopt` or lets it request membership with `user.request_membership`; a
node accepts an inbound contract with `user.accept_membership`. A user
permanently bans a node with `user.expel`, and the list of bans is inspectable
via `user.list_expelled`. Banned nodes hold a `mod.user.signed_expulsion` and
are refused new contracts.
