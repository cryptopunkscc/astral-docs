# bip137sig.seed

A 64-byte BIP-39 seed derived from a mnemonic via PBKDF2-HMAC-SHA512. Suitable as the root for BIP-32 key derivation.

## Encoding

* Binary: a `uint8` length byte (always `64`) followed by the seed bytes.
* Text/JSON: lowercase hex string (128 chars).

## Example

```json
{
  "Type": "bip137sig.seed",
  "Object": "5eed0102030405060708090a0b0c0d0e0f101112131415161718191a1b1c1d1e1f202122232425262728292a2b2c2d2e2f303132333435363738393a3b3c3d3e3f"
}
```
