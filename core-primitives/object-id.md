# Object ID

* The `Object ID` is a 320-bit value consisting of the `Object Size` (uint64) 
  followed by the `Object Hash` (SHA256).
* The `Object Size` is the size of the object encoded using the `Binary 
Encoding`.
* The `Object Hash` is the SHA256 hash of the object encoded using the `Binary 
Encoding`.
* The `Object ID` is calculated by:
  * encoding the 320-bit value using zBase32 with character set 
    "ybndrfg8ejkmcpqxot1uwisza345h769"
  * removing the leading "y"s from the string
  * adding a "data1" prefix
* The `Object Hash` of an `Empty Object` is the SHA256 hash of an empty byte 
  buffer.
