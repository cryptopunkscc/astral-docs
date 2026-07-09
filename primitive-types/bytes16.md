# bytes16

Basic byte-array type, equivalent to bytes8, bytes32, and bytes64 in JSON. Differs from those only in the width of the length prefix.

## Binary Encoding

A uint16 length prefix followed by that many raw bytes.

## JSON Encoding

A base64 string.

## Text Encoding

A base64 string.
