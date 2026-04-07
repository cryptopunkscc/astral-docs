# Object ID

* The `Object ID` consists of the `Size` (uint64) and the `Hash` (32 bytes).
* The `Size` is the length of the `Payload` in bytes.
* The `Hash` is a SHA256 hash of the `Payload`.
* The `Object ID` is encoded using zBase32 encoding with `data1` prefix.
* The `Hash` of an `Empty Object` is the SHA256 hash of an empty byte buffer.
