# Bundle

* A `Bundle` is an ordered collection of unique [`Objects`](object.md) of various types.
* A `Bundle` is itself an [`Object`](object.md); its [`Object Type`](object-type.md) is `bundle`.
* An `Object` appears at most once in a `Bundle`.
* A `Bundle` preserves the order in which `Objects` were added.
* `Bundles` are used wherever a single `Object` must carry a set of others — for
  example, the constraints of a [`Permit`](permit.md).
