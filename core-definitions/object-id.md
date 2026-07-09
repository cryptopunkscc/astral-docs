# Object ID

* The `Object ID` is a 320-bit value consisting of the `Object Size` (uint64) 
  followed by the `Object Hash` (SHA256).
* For a `Typed Object` the `Object Size` and `Object Hash` cover the object's
  `Canonical Form` — the [`Stamp`](stamp.md), then the object type as a
  [`string8`](../primitive-types/string8.md), then the payload (see
  [Codec](../topics/codec.md)).
* For an `Untyped Object` the `Object Size` and `Object Hash` cover the raw
  payload.
* The `Object Size` is the length in bytes of that byte sequence.
* The `Object Hash` is the SHA256 hash of that byte sequence.
* The `Object ID` is calculated by:
  * encoding the 320-bit value using zBase32 with character set 
    "ybndrfg8ejkmcpqxot1uwisza345h769"
  * removing the leading "y"s from the string
  * adding a "data1" prefix
* The `Object Hash` of an `Empty Object` is the SHA256 hash of an empty byte 
  buffer.
