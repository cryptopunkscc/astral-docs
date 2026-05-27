# mod.nodes.endpoint_with_ttl

An `exonet.Endpoint` paired with an optional time-to-live in seconds. A nil `TTL` means the endpoint does not expire.

## Fields

* Endpoint (object) – The underlying `exonet.Endpoint` (e.g. `tcp.endpoint`, `tor.endpoint`, `gateway.endpoint`, `utp.endpoint`).
* TTL (uint32) – Lifetime of the endpoint in seconds, or null if it does not expire.

## Example

```json
{
  "Type": "mod.nodes.endpoint_with_ttl",
  "Object": {
    "Endpoint": {
      "Type": "tcp.endpoint",
      "Object": "1.2.3.4:1791"
    },
    "TTL": 7776000
  }
}
```
