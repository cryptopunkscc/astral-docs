# Binary Encoding

* The `Binary Encoding` is the default and standard encoding used by the `Astral
  Network`.
* The `Binary Encoding` uses the Big Endian byte order.
* The `Binary Encoding` of an `Object` is done by writing bytes:
    * If the `Object Type` is non-empty, write the `Object Header` first:
        * Write the `Stamp`
        * Write the `Object Type` as an 8-bit length encoded ASCII string.
    * Write the `Payload` data.

## Arrays

* Arrays are encoded using a `uint32` length-prefix. An array of 3 `uint8` 
  values [1, 2, 3] is encoded as: 00 00 00 03 01 02 03.