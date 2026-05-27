# crypto.public_key

Derive the public key for a private key passed via the input stream.

## Arguments

* in (string) – Optional input stream format (e.g. `json`).
* out (string) – Optional output stream format (e.g. `json`).
* (stream) – A `mod.crypto.private_key` object to derive the public key from.

## Returned objects

The operation returns one of:
* An `error_message` object if the key could not be decoded or no engine supports its type.
* A `mod.crypto.public_key` object containing the derived public key.

## Examples

```shellsession
$ echo '{"Type":"mod.crypto.private_key","Object":"secp256k1:Yt+8a1q4XbPnGZsbT5gV/Sj5y4kCmWNL2L4y3rXh0vQ="}' | astral-query crypto.public_key -in json -out json
{"Type":"mod.crypto.public_key","Object":"secp256k1:02bef8840eb35ef2ae3c83c07cb5779278904f99cb4103f71e37cc69931ae5e15f"}
```
