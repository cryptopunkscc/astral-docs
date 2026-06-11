# mod.kcp.endpoint_local_mapping

A mapping from a remote KCP endpoint address to a local UDP port.

## Fields

* Address (string8) – The remote endpoint address string (e.g. `203.0.113.10:7000`).
* Port (uint16) – The local UDP port mapped to that remote endpoint.

## Example

```json
{
  "Type": "mod.kcp.endpoint_local_mapping",
  "Object": {
    "Address": "203.0.113.10:7000",
    "Port": 8000
  }
}
```
