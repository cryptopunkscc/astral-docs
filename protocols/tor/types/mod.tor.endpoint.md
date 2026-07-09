# mod.tor.endpoint

A Tor transport endpoint, identifying a node by its onion-service digest and a port.

## Fields

* Digest (mod.tor.digest) – The onion-service identifier of the node.
* Port (uint16) – The port number on the onion service.

The text form is `<digest>:<port>`, where the digest renders as its `.onion` hostname; JSON encodes the object as that same text. A zero-value endpoint has the text form `unknown`.

## Example

```json
{
  "Type": "mod.tor.endpoint",
  "Object": "aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaad.onion:1791"
}
```
