# Query

* A `Query` is used by `Identities` to call each other's `Operations`.
* A `Query` has `Caller` and `Target` identities, and a `Query String`.
* A `Query` can be routed by various means: directly via `Links`, relayed via
  `Nodes`, as well as other means.
* The `Target` can reject the `Query` with a non-zero uint8 `Reject Code`.
* The generic and default `Reject Code` is 1. Other values are `Operation`
  specific.
* The `Target` can accept the `Query`, which begins a new `Channel` between
  the `Caller` and the `Target`.
