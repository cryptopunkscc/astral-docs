# nearby

The `nearby` protocol discovers and tracks nodes reachable on the local network. Nodes periodically broadcast a `mod.nearby.status_message` carrying a bundle of attached objects composed by registered `Composer` implementations; the module caches incoming broadcasts and expires them after five minutes.

Three broadcast modes are supported via `mod.nearby.mode`: `silent` suppresses all broadcasts, `visible` broadcasts the full public profile including a `mod.nearby.public_profile` attachment, and `stealth` broadcasts a `mod.nearby.stealth_hint` that masks the node–user association so only nodes that know the user identity can deanonymize the hint. Stealth mode is suppressed when no attachments are present.

Two ops are exposed: `nearby.broadcast` triggers an immediate push of the local node's status, and `nearby.list` streams the cached `mod.nearby.status` of all currently known nearby peers.
