# Text Encoding

* The `Text Encoding` is an encoding that is used by the `Astral
  Network`.
* The `Text Encoding` encodes its payload using Base64 encoding.
* The `Text Encoding` can have a type-specific encoding of the payload,
  which must be specified in the documentation of the `Object Type`.
* The `Text Encoding` can be used to encode objects as
  [`Query`](../core-primitives/query-string.md) parameters.
* The `Text Encoding` is done by concatenating the following:
    * A string with the format "#[{OBJECT_TYPE}]", for example "#[uint32]".
    * A single character indicating the encoding type: ":" for Base64, " " for
      type-specific encoding.
    * The encoded payload.
* The `Text Encoding` of an `Untyped Object` is "#[]:" followed by the
  Base64-encoded `Payload`.
* A `Typed Object` with no payload is encoded as `#[{OBJECT_TYPE}]`.


