# nat.punch_signal

A control message exchanged over the signalling channel while two peers coordinate a hole-punch. The `signal` field selects one of five handshake steps, sent in order: `offer` (the initiator advertises its endpoint and opens a session), `answer` (the passive peer advertises its endpoint), `ready` (the passive peer is listening), `go` (both peers punch simultaneously), and `result` (the observed endpoint and hole nonce are confirmed).

## Fields

* signal (string8) – The handshake step: one of `offer`, `answer`, `ready`, `go`, `result`.
* session (bytes8) – Session token that binds the exchange; established by the `offer` and echoed by every later signal.
* ip (bytes8) – The sender's advertised IP address (IPv4 stored as 4 bytes, IPv6 as 16 bytes).
* port (uint16) – The sender's advertised UDP port.
* pair_nonce (nonce64) – The nonce assigned to the resulting hole; carried by the `result` signal.

## Example

```json
{
  "Type": "nat.punch_signal",
  "Object": {
    "signal": "offer",
    "session": "8fA1b2c3d4e5f6A=",
    "ip": "198.51.100.7",
    "port": 41000,
    "pair_nonce": "0"
  }
}
```
