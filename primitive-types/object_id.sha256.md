# object_id.sha256

An object ID consisting of a `Size` (uint64) and a `Hash` (SHA-256, 32 bytes).

* The `Size` is the length of the payload in bytes.
* The `Hash` is the SHA-256 hash of the payload.

## Binary Encoding

40 bytes: the `Size` as a big-endian uint64 (8 bytes) followed by the 32-byte SHA-256 hash.

## JSON Encoding

A zBase32-encoded string of the binary representation, prefixed with `data1`.

## Text Encoding

A zBase32-encoded string of the binary representation, prefixed with `data1`.
