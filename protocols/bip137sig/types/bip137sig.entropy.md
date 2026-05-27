# bip137sig.entropy

Raw entropy bytes used to seed a BIP-39 mnemonic.

## Encoding

* Binary: a `uint8` length byte followed by the entropy bytes.
* Text/JSON: lowercase hex string.

Valid lengths are 16, 20, 24, 28, or 32 bytes (128–256 bits in 32-bit steps).

## Example

```json
{
  "Type": "bip137sig.entropy",
  "Object": "a1b2c3d4e5f60718293a4b5c6d7e8f90"
}
```
