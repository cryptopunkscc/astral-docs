# mod.nodes.observed_endpoint_message

A message pushed to a peer to tell them which endpoint we observed for their inbound link. Lets the peer learn its public address.

## Fields

* Endpoint (object) – The observed `exonet.Endpoint`. Encoded as a generic astral object on the wire (type + payload), not pre-tagged.

## Example

```json
{
  "Type": "mod.nodes.observed_endpoint_message",
  "Object": {
    "Endpoint": {
      "Type": "tcp.endpoint",
      "Object": "1.2.3.4:1791"
    }
  }
}
```
