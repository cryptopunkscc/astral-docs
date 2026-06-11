# mod.tcp.endpoint

A TCP endpoint consisting of an IP address and a port number.

## Fields

* IP (bytes8) – IP address; 4 bytes for IPv4, 16 bytes for IPv6.
* Port (uint16) – TCP port number.

The text form is `<ip>:<port>`; JSON encodes the object as that same text.

## Example

```json
{
  "Type": "mod.tcp.endpoint",
  "Object": "1.2.3.4:1791"
}
```
