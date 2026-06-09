# Blueprints

* A `Blueprint` describes a `Typed Object`'s wire structure so the `Codec` reads or writes it without compiled code.
* Every `Object Type` known to a `Node` is backed by a compile-time prototype or a `Blueprint`, both held in one registry keyed by `Object Type`.

## Kinds

* `Struct` — ordered named `Fields`; wire is each field's value in declared order.
* `Alias` — names an existing primitive; wire is identical to the underlying primitive.

## Specs

* Each `Field` has a `Name` and one `Spec`:
    * `PrimitiveSpec` — primitive from the allowlist.
    * `RefSpec` — another registered `Object Type`.
    * `SliceSpec` — `uint32` count + elements.
    * `ArraySpec` — elements only; length is in the schema.
    * `MapSpec` — `uint32` count + sorted key/value pairs.
    * `PtrSpec` — [`bool`](../common-types/bool.md) presence + value if present.
    * `ObjectSpec` — [`string8`](../common-types/string8.md) type tag + payload.
* `Slice/Array/MapSpec` with empty element or value type → heterogeneous; each element carries its own type tag.
* Primitive allowlist: `stringN` / `uintN` / `bytesN` (`N` ∈ {8, 16, 32, 64}), `bool`,
  [`time`](../common-types/time.md),
  [`identity`](../common-types/identity.md),
  [`object_id.sha256`](../common-types/object_id.sha256.md),
  [`nonce64`](../common-types/nonce64.md), `duration`, `zone`.
* `MapSpec.KeyType` is [`string16`](../common-types/string16.md) or `uintN` (`N` ∈ {8, 16, 32, 64}).

## Registry

* Maps `Object Type` → `Blueprint` or prototype. Names are unique and immutable.
* A registry can have a `Parent`; lookups walk the chain, local entries shadow.
* `Object Type` names are ASCII non-empty. `Field Names` are ASCII non-empty, unique within a `Blueprint` (case-insensitive).
* A `Blueprint` is itself an `Object`; registering returns the [`Object ID`](../core-primitives/object-id.md) of its canonical form.
* Nested types resolve through the same registry given to the enclosing `Decode`.

## Sync

* Exchanged in dependency order: aliases first, then structs topologically sorted so every `RefSpec`/`PtrSpec`/`SliceSpec`/`ArraySpec`/`MapSpec` edge targets an already-replayed name.
* Replay compares by `Object ID`: same name + matching ID is a no-op, same name + mismatched bytes is a conflict.

## Limits

* Nested `Blueprint` frames are capped; `RefSpec`/`PtrSpec` cycles surface as typed errors.
* `ArraySpec.Length` and registered name lengths are bounded.
* `Aliases` over `Struct Blueprints` are not supported.
