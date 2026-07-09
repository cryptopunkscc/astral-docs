# nat.endpoint

A NAT traversal endpoint, identified by a UDP host and port.

## Fields

* IP (bytes8) – The IP address (IPv4 stored as 4 bytes, IPv6 as 16 bytes).
* Port (uint16) – The UDP port number.

The text form is `<host>:<port>`; JSON encodes the object as its named fields.

## Example

```json
{
  "Type": "nat.endpoint",
  "Object": {
    "IP": "198.51.100.7",
    "Port": 41000
  }
}
```
