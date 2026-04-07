# Binary Encoding

* The `Binary Encoding` is the default and standard encoding used by the `Astral
  Network`.
* The `Binary Encoding` uses the Big Endian byte order.
* The `Binary Encoding` of an `Object` is done by writing bytes:
    * Only if the `Object Type` is non-empty:
        * Write the `Stamp`
        * Write the `Object Type` as an 8-bit length encoded ASCII string.
    * Write the `Payload` data.
