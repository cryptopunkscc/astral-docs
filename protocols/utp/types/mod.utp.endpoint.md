# mod.utp.endpoint

A uTP transport endpoint, identifying a host by an IP address and a UDP port.

## Fields

* IP (bytes8) – The IP address (IPv4 stored as 4 bytes, IPv6 as 16 bytes).
* Port (uint16) – The UDP port number.

The network name of a uTP endpoint is always `utp`. The text form is `<host>:<port>`; JSON encodes the object as that same text.

## Example

```json
{
  "Type": "mod.utp.endpoint",
  "Object": "203.0.113.10:7000"
}
```
