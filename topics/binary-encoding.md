# Binary Encoding

* The `Binary Encoding` is the default and standard encoding used by the
  `Astral Network`.
* The `Binary Encoding` uses the Big Endian byte order. Signed integers
  use two's complement.
* The `Binary Encoding` defines the `Payload` bytes only. Framing of a
  typed object — the bytes that announce the [`Object Type`](../core-definitions/object-type.md) in front of
  the `Payload` — is covered in [Codec](codec.md).

## Primitives

* Fixed-width integers are written as their natural width in Big Endian.
  [`uint8`](../primitive-types/uint8.md) is 1 byte,
  [`uint16`](../primitive-types/uint16.md) is 2 bytes,
  [`uint32`](../primitive-types/uint32.md) is 4 bytes,
  [`uint64`](../primitive-types/uint64.md) is 8 bytes.
* Length-prefixed primitives come in four widths:
  [`string8`](../primitive-types/string8.md)/`bytes8` use a `uint8` length,
  [`string16`](../primitive-types/string16.md)/`bytes16` use `uint16`,
  [`string32`](../primitive-types/string32.md)/`bytes32` use `uint32`,
  [`string64`](../primitive-types/string64.md)/`bytes64` use `uint64`. The
  width is part of the `Object Type`; payload caps follow the width
  (255, 65 535, 2³²−1, 2⁶⁴−1).
* `Structured` objects are written field by field in the order declared
  by the schema; field names are not on the wire.

## Slices

* Encoded as a `uint32` count followed by each element.

```
[]uint32{1, 2, 0xDEADBEEF}             → 19 bytes

   00 00 00 03                count = 3 (uint32)
   01 00 00 00 01             [0] presence + uint32 = 1
   01 00 00 00 02             [1] presence + uint32 = 2
   01 de ad be ef             [2] presence + uint32 = 0xDEADBEEF
```

## Arrays

* Encoded as a sequence of elements; the length lives in the schema and
  is not on the wire.

```
[2]uint16{1, 2}                        → 6 bytes
                                         (no count; length is in the schema)
   01 00 01                   [0] presence + uint16 = 1
   01 00 02                   [1] presence + uint16 = 2
```

## Maps

* Keys must be `string16` or `uintN` (`N` ∈ {8, 16, 32, 64}). No other key
  type is encodable. Integer keys are fixed-width Big Endian, string keys
  are `string16`.
* Encoded as a `uint32` count followed by key/value pairs.

```
map[string16]uint8{"ab": 2, "hi": 1}   → 16 bytes

   00 00 00 02                count = 2 (uint32)
   00 02 61 62                key   — string16 "ab"
   01 02                      value — presence + uint8 = 2
   00 02 68 69                key   — string16 "hi"
   01 01                      value — presence + uint8 = 1
```

### Sort order

* Entries are written in ascending order of their encoded key bytes. The
  order is part of the wire format — two `Maps` with the same entries
  produce identical bytes regardless of insertion order, which keeps
  content hashes stable.

```
Map sort — map[uint16]uint8{1: 0xa, 7: 0xb, 256: 0xc}

   00 00 00 03                count = 3 (uint32)
   00 01                      key — uint16 = 1
   01 0a                      value — presence + uint8 = 0xa
   00 07                      key — uint16 = 7
   01 0b                      value — presence + uint8 = 0xb
   01 00                      key — uint16 = 256
   01 0c                      value — presence + uint8 = 0xc

   keys ascend by byte: 00 01 < 00 07 < 01 00
```

## Optional values

* Inside a `Slice`, `Array`, or `Map` value-half, each non-pointer
  non-interface element is preceded by a `0x01` presence byte so that a
  sequence of values and a sequence of optionals produce identical bytes
  for present elements.
* Encoded as a [`bool`](../primitive-types/bool.md) presence flag followed
  by the value when present.

```
Optional uint16

   00                         absent                        (1 byte)
   01 00 2a                   present + uint16 = 42         (3 bytes)
```

### Presence flag values

* `0x00` (absent) or `0x01` (present). Any other value is rejected as
  corrupt.

```
Presence flag value range

   00                         absent     — accepted
   01                         present    — accepted
   02 .. ff                   any other  — rejected as corrupt
```

## Polymorphic fields

* Polymorphic fields and interface-typed elements carry a type tag inline:
  the element is written as `Object Type` (a `string8`) followed by the
  `Payload`. A zero-length `Object Type` denotes nil. A non-nil value must
  have a non-empty `Object Type`.

```
Polymorphic Object

   05 75 69 6e 74 38 07       string8 type "uint8" + uint8 = 7   (7 bytes)
   00                         nil — zero-length type tag         (1 byte)
```
