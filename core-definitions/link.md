# Link

* A `Link` is a connection between two [`Nodes`](node.md).
* A `Link` can carry [`Queries`](query.md) and [`Channel`](channel.md) data between the two parties.
* A `Link` can be established over an [`Exonet`](exonet.md) or some other means of binary
  data exchange.
* A `Link` is multiplexed and can handle multiple `Channels` simultaneously.
* A `Link` is authenticated so `Nodes` know who they are talking to.
* A `Link` is encrypted and provides protection for all the data it carries.
* A `Link` uses the Noise XK protocol for authentication and encryption by
  default, but any protocol can be used as long as both parties agree on it
  (which can happen out-of-band).
* The Noise XK static keys are the peers' [`Identity`](identity.md) secp256k1 key
  pairs; there is no separate handshake key. The initiator therefore commits to
  the responder's `Identity` before the handshake begins.
