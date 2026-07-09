# mod.tor.digest

The onion-service identifier of a Tor node, from which its `.onion` hostname is derived.

## Fields

The type has no named struct fields. On the wire the digest is exactly 35 raw bytes with no length prefix. The text form is the digest encoded as lowercase base32 with the `.onion` suffix appended; JSON encodes the object as that same text.

## Example

```json
{
  "Type": "mod.tor.digest",
  "Object": "aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaad.onion"
}
```
