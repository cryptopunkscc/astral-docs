# tor

The `tor` protocol provides onion-service transport for astral node connectivity. It dials and accepts connections through the Tor network, reaching each remote node by its onion-service address rather than by a routable IP.

Endpoints are represented as `mod.tor.endpoint` objects, each pairing a `mod.tor.digest` (the onion-service identifier, rendered as an `.onion` address) with a port number. The digest is the fixed-length service descriptor from which the human-readable `.onion` hostname is derived.
