# nat.consume_hole_signal

A control message exchanged over the signalling channel during the two-phase handshake that hands a hole out of the pool. The `Signal` field selects one of four steps, sent in order: the initiator sends `lock` and the holder replies `locked`; the initiator then sends `take` and the holder replies `taken`. A reply carries `Ok` false and an `Error` string when the holder cannot satisfy the request.

## Fields

* Signal (string8) – The handshake step: one of `lock`, `locked`, `take`, `taken`.
* Pair (nonce64) – The nonce of the hole being consumed; must match on both sides.
* Ok (bool) – Set on `locked` and `taken` replies to indicate success; false when the request failed.
* Error (string8) – Failure reason, present only when `Ok` is false; empty otherwise.

## Example

```json
{
  "Type": "nat.consume_hole_signal",
  "Object": {
    "Signal": "locked",
    "Pair": "3fa1c0de9b7e0011",
    "Ok": true,
    "Error": ""
  }
}
```
