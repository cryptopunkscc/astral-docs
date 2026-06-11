# mod.nearby.stealth_hint

Broadcast in stealth mode to allow nodes that know the user identity to recover the node identity, while hiding the user–node association from others.

## Fields

* Commitment ([]uint8) – SHA-256 of SHA-256(compressed userID public key) concatenated with the nonce, encoded as a length-prefixed byte slice.
* MaskedID ([]uint8) – The node's compressed public key XOR-ed with the user's compressed public key, encoded as a length-prefixed byte slice.
* Nonce (nonce64) – Random nonce used in the commitment.

## Example

```json
{
  "Type": "mod.nearby.stealth_hint",
  "Object": {
    "Commitment": "3q2+7wAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA=",
    "MaskedID": "A7+YhA6zXvKuPIPAfLV3kniQT5nLQQP3HjfMaZMa5eF=",
    "Nonce": "7c1a93b50f2e4d18"
  }
}
```
