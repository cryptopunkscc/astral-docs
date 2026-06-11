# mod.ip.ip_address

An IPv4 or IPv6 address.

## Fields

The type has no named struct fields. On the wire it encodes as a length-prefixed byte slice (`bytes8`): 4 bytes for an IPv4 address, 16 bytes for an IPv6 address. JSON and text forms encode as a dotted-decimal or colon-separated string.

## Example

```json
{
  "Type": "mod.ip.ip_address",
  "Object": "192.168.1.42"
}
```
