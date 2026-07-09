# identity

Represented by a 66-digit hex string of a secp256k1 public key.

## Anonymous identity

The all-zero 33-byte key is the anonymous identity ("anyone"). Two anonymous identities compare equal.

## Binary Encoding

The binary encoding of an identity is 33 bytes of the raw secp256k1 public key.

The binary encoding of the anonymous identity is 33 zero bytes.

## JSON Encoding

The JSON encoding of an identity is the hex string of the secp256k1 public key.

The JSON encoding of the anonymous identity is the string `"anyone"`, which is also accepted on parse.

## Text Encoding

The text encoding of an identity is the hex string of the secp256k1 public key.

The text encoding of the anonymous identity is the 66-zero hex string. Parsing accepts either the literal string `anyone` or 66 `0` hex characters.