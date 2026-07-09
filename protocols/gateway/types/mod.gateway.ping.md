# mod.gateway.ping

A gateway connection-control frame that keeps an idle connection alive. Both
sides of a connection routed through the [`gateway`](../README.md) protocol
exchange these frames: a frame with `Pong` set to false is a keepalive request,
and a frame with `Pong` set to true is the reply to such a request. A request
that receives no timely reply causes the connection to close.

## Fields

* Pong (bool) – False marks a keepalive request; true marks the reply to a request.

## Example

```json
{
  "Type": "mod.gateway.ping",
  "Object": {
    "Pong": false
  }
}
```
