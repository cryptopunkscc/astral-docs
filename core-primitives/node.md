# Node

* A `Node` is an active agent on the `Astral Network`.
* A `Node` can establish a [`Link`](link.md) to another `Node` over an [`Exonet`](exonet.md).
* A `Node` can host [`Apps`](app.md).
* A `Node` relays [`Queries`](query.md) and [`Channel`](channel.md) data for the `Apps` it hosts.
* A `Node` assigns [`Identities`](identity.md) to the `Apps` it hosts that are valid until
  the `App` is removed from the `Node`.
* A `Node` manages the cryptographic keys of the `Apps` it hosts.
* A `Node` and its `Apps` produce signed [`Objects`](object.md) that can be used to prove
  to other `Identities` that the `Node` hosts those `Apps`.
