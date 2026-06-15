# Zone

* A `Zone` scopes where a [`Query`](query.md) or [`Operation`](op.md) may be routed and
  resolved.
* There are three `Zones`:
  * `Device` — local to the [`Node`](node.md) itself: its own storage and hosted
    [`Apps`](app.md).
  * `Virtual` — the `Node`'s virtual providers, which are neither device-local nor
    on the network.
  * `Network` — other [`Nodes`](node.md), reached over [`Links`](link.md).
* A `Zone` is a set: any combination of the three can be permitted at once.
* An `Operation` that accepts a `Zone` treats it as a filter; the default is all
  `Zones`.
* The `Network` `Zone` is stripped from untrusted queries (e.g. anonymous guests),
  confining them to the local `Node`.
* A `Zone` is written in text as a string of `d`, `v`, `n` (e.g. `dvn`), and on the
  wire as a [`uint8`](../primitive-types/uint8.md) bit field.
