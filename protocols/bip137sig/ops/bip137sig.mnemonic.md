# bip137sig.mnemonic

Convert entropy bytes into a BIP-39 mnemonic phrase. The checksum is appended automatically.

## Arguments

* (stream) – A `bip137sig.entropy` object to encode.

## Returned objects

The operation returns one of:
* An `error_message` object if the entropy size is invalid.
* A `string16` object containing the mnemonic words joined by single spaces (12, 15, 18, 21, or 24 words depending on entropy length).

## Examples

```shellsession
$ echo '{"Type":"bip137sig.entropy","Object":"a1b2c3d4e5f60718293a4b5c6d7e8f90"}' \
    | astral-query bip137sig.mnemonic -in json -out json
{"Type":"string16","Object":"penalty stadium garlic ... rifle fitness garage"}
```
