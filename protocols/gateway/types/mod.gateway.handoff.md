# mod.gateway.handoff

A gateway connection-control frame the gateway sends to an idle connection to
trigger the activation handshake. On receiving it the peer replies with a
[`mod.gateway.handoff_ack`](mod.gateway.handoff_ack.md) frame, after which both
sides leave idle mode and the connection begins carrying data. See the
[`gateway`](../README.md) protocol for how idle connections are established and
activated.

## Fields

This frame carries no fields.

## Example

```json
{
  "Type": "mod.gateway.handoff",
  "Object": {}
}
```
