# mod.crypto.public_key

A typed public key used to verify signatures and identify signers.

## Fields

* Type (string8) – Name of the key scheme (e.g. `secp256k1`).
* Key (bytes16) – Raw public-key bytes for the given scheme.

The text form is `<type>:<hex-encoded key>`; JSON encodes the object as that same text.

## Example

```json
{
  "Type": "mod.crypto.public_key",
  "Object": "secp256k1:02bef8840eb35ef2ae3c83c07cb5779278904f99cb4103f71e37cc69931ae5e15f"
}
```
