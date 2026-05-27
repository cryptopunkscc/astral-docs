# mod.nodes.migrate_signal

A signalling message exchanged during session migration. The `Buffer` field carries the sender's receive-buffer size so the peer can size its write window.

## Fields

* Signal (string8) – One of `ready`, `switched`, `resume`, or `done`. Marks the current step of the migration handshake.
* Buffer (uint32) – Receive-buffer size, in bytes, advertised by the sender.

## Example

```json
{
  "Type": "mod.nodes.migrate_signal",
  "Object": {
    "Signal": "ready",
    "Buffer": 4194304
  }
}
```
