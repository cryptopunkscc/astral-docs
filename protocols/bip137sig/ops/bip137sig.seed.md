# bip137sig.seed

Convert a BIP-39 mnemonic phrase into a 64-byte seed using PBKDF2-HMAC-SHA512 (2048 iterations, salt `mnemonic` + passphrase). The mnemonic is validated against the BIP-39 checksum before derivation.

## Arguments

* passphrase (string) – Optional BIP-39 passphrase ("25th word"). Defaults to empty.
* (stream) – A `string16` object containing the mnemonic words separated by whitespace.

## Returned objects

The operation returns one of:
* An `error_message` object if the mnemonic word count is wrong, an unknown word is used, or the checksum does not match.
* A `bip137sig.seed` object containing the 64-byte seed.

## Examples

```shellsession
$ echo '{"Type":"string16","Object":"penalty stadium garlic ... rifle fitness garage"}' \
    | astral-query bip137sig.seed -in json -out json
{"Type":"bip137sig.seed","Object":"5eed0102...64bytes...cafef00d"}
```

```shellsession
$ echo '{"Type":"string16","Object":"penalty stadium garlic ... rifle fitness garage"}' \
    | astral-query bip137sig.seed -passphrase correcthorse -in json -out json
{"Type":"bip137sig.seed","Object":"9d40ab12...64bytes...77a3"}
```
