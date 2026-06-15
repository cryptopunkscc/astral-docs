# Permit

* A `Permit` is a single capability granted by a [`Contract`](contract.md).
* A `Permit` names the [`Object Type`](object-type.md) of an action it authorises.
* A `Permit` may carry an optional [`Bundle`](bundle.md) of constraints that narrow the
  grant.
* When the permitted action supports constraints, it evaluates the constraints to
  decide whether the `Permit` applies; actions that do not are permitted
  unconditionally.
* See the wire type [`mod.auth.permit`](../protocols/auth/types/mod.auth.permit.md).
