# mod.crypto.hash

A raw byte hash used as input to and output of signature operations.

## Encoding

* Binary: a `bytes8` length-prefixed byte slice.
* Text/JSON: lowercase hex string.

The length is not fixed by the type; it is determined by the hashing scheme used by the caller (e.g. 32 bytes for SHA-256).

## Example

```json
{
  "Type": "mod.crypto.hash",
  "Object": "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
}
```
