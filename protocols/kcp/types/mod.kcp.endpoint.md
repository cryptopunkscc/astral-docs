# mod.kcp.endpoint

A KCP transport endpoint, identified by a UDP host and port.

## Fields

* IP (bytes8) – The IP address (IPv4 stored as 4 bytes, IPv6 as 16 bytes).
* Port (uint16) – The UDP port number.

The text form is `<host>:<port>`; JSON encodes the object as that same text.

## Example

```json
{
  "Type": "mod.kcp.endpoint",
  "Object": "203.0.113.10:7000"
}
```
