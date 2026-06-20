# mod.crypto.signature

A generic container for a signature, tagged with the scheme that produced it.

## Fields

* Scheme (string8) – Name of the signature scheme (e.g. `asn1`, `bip137`).
* Data (bytes16) – Raw signature bytes for the given scheme.

The text form is `<scheme>:<base64-encoded data>`; JSON encodes the object as that same text.

## Example

```json
{
  "Type": "mod.crypto.signature",
  "Object": "asn1:MEUCIQDg+5p9aT4q2QzVKbS9N5wXYrFh3vUaQ7E2lY0bX9pSAiB7H1k0kZl0ZTd5KQv0pZL5kE2c8R5Mz0qY1g6kPq3rTfM="
}
```
