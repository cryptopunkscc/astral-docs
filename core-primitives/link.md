# Link

* A `Link` is a connection between two `Nodes`.
* A `Link` can carry `Queries` and `Channel` data between the two parties.
* A `Link` can be established over an `Exonet` or some other means of binary
  data exchange.
* A `Link` is multiplexed and can handle multiple `Channels` simultaneously.
* A `Link` is authenticated so `Nodes` know who they are talking to.
* A `Link` is encrypted and provides protection for all the data it carries.
* A `Link` uses the Noise XK protocol for authentication and encryption by
  default, but any protocol can be used as long as both parties agree on it
  (which can happen out-of-band).
