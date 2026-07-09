# mod.gateway.handoff_ack

A gateway connection-control frame a peer sends to confirm it received a
[`mod.gateway.handoff`](mod.gateway.handoff.md). After sending this frame the
idle connection transitions to an active, data-carrying state. See the
[`gateway`](../README.md) protocol for the surrounding activation handshake.

## Fields

This frame carries no fields.

## Example

```json
{
  "Type": "mod.gateway.handoff_ack",
  "Object": {}
}
```
