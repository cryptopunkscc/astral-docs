# Node Setup

* A fresh `Node` runs without a `User` identity. The daemon auto-generates
  a `secp256k1` node key on first start; until an active node contract is
  installed, the node operates only under its own identity.
* A `Node` joins a `User`'s swarm by holding an active
  `mod.user.swarm_access_action` contract — an
  [`mod.auth.signed_contract`](../protocols/user/types/mod.user.swarm_access_action.md)
  with the `User` as `Issuer` and the `Node` as `Subject`, stored at the
  `tree` path `/mod/user/config/active_contract`.
* Bootstrap means: (1) obtain a `User` identity, (2) build and sign a node
  contract, (3) write it to the active-contract path.
* The `User` key can live in software (BIP-39 seed indexed by `crypto`) or
  in hardware (Coldcard signing via BIP-137).

## Software User (no Coldcard)

1. Generate entropy and derive a `secp256k1` private key:
    * [`bip137sig.new_entropy`](../protocols/bip137sig/ops/bip137sig.new_entropy.md)
      → [`bip137sig.mnemonic`](../protocols/bip137sig/ops/bip137sig.mnemonic.md)
      → [`bip137sig.seed`](../protocols/bip137sig/ops/bip137sig.seed.md)
      → [`bip137sig.derive_key`](../protocols/bip137sig/ops/bip137sig.derive_key.md).
    * The mnemonic is the user's backup; store it out-of-band.
2. Store the `crypto.private_key` via
   [`objects.store`](../protocols/objects/ops/objects.store.md) into a
   repository scanned by the `crypto` module (default: `local`, `system`,
   `mem0`). The module auto-indexes the key on insert, so it becomes usable
   as a signer for the corresponding public key.
3. Derive the `User`'s `Identity` via
   [`crypto.public_key`](../protocols/crypto/ops/crypto.public_key.md) over
   the private key. The hex of the `secp256k1` public key is the `User`
   identity.
4. Optionally register an alias for the `User` via
   [`dir.set_alias`](../protocols/dir/ops/dir.set_alias.md).
5. Build an unsigned contract with
   [`user.new_node_contract`](../protocols/user/ops/user.new_node_contract.md)
   passing `-user <user-id-or-alias>` (subject defaults to the local node).
6. Sign as both issuer and subject with `auth.sign_contract` (both keys are
   local; the call uses `ASN1` for the software user key and the node key).
7. Install the resulting `mod.auth.signed_contract` as the active contract
   via [`tree.set`](../protocols/tree/ops/tree.set.md) at path
   `/mod/user/config/active_contract`.
8. Verify with
   [`user.info`](../protocols/user/ops/user.info.md) — it returns the user
   alias, node alias, and active contract id.

## Hardware User (Coldcard)

* The `coldcard` module exposes the `secp256k1` public key at BIP-44 path
  `m/1791'/0'/0'/0/0` and registers a `crypto` engine that produces
  `BIP-137` text signatures on the device. No private key is ever stored
  on the node.
* The device must be unlocked and connected before scanning.

1. Trigger discovery with `coldcard.scan` (also runs once at module
   start). The log emits `found coldcard device: <serial> for key
   <pubkey-hex>`.
2. The public key hex is the `User` `Identity`. Optionally alias it via
   [`dir.set_alias`](../protocols/dir/ops/dir.set_alias.md).
3. Build an unsigned contract with
   [`user.new_node_contract`](../protocols/user/ops/user.new_node_contract.md)
   passing `-user <coldcard-pubkey-or-alias>`.
4. Sign with `auth.sign_contract`. Two signatures are produced:
    * Issuer (`User`) – the `coldcard` engine's `BIP-137` `TextSigner`
      prompts the device to confirm and sign.
    * Subject (`Node`) – the local node key signs as `ASN1`.
   Mixed schemes within one `mod.auth.signed_contract` are supported;
   verification dispatches per signature scheme.
5. Install the signed contract via
   [`tree.set`](../protocols/tree/ops/tree.set.md) at
   `/mod/user/config/active_contract`.
6. Verify with
   [`user.info`](../protocols/user/ops/user.info.md).

## Adding More Nodes to the Swarm

Once one node is active under a `User`, other unclaimed nodes join the same
swarm without re-bootstrapping the `User`:

* From the active node, acting as the `User`:
  [`user.claim`](../protocols/user/ops/user.claim.md) `-target <node>`.
* From an unclaimed node, asking to be admitted:
  [`user.request_invite`](../protocols/user/ops/user.request_invite.md)
  against any active swarm node.
* Both paths exchange a fresh contract through
  [`user.invite`](../protocols/user/ops/user.invite.md) on the joining
  node, which installs the active contract on success.
