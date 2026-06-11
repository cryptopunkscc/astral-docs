# secp256k1

The `secp256k1` protocol adds secp256k1 elliptic-curve key support to the `crypto` module. It registers a `crypto.Engine` that handles `secp256k1`-typed `mod.crypto.private_key` and `mod.crypto.public_key` objects, and provides ASN1-encoded ECDSA hash signing and verification.

The single operation `secp256k1.new` generates a fresh private key and returns it as a `mod.crypto.private_key` object.
