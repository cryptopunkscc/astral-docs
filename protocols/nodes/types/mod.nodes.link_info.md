# mod.nodes.link_info

Describes a single active link between two identities.

## Fields

* ID (nonce64) – Local id of the link.
* LocalIdentity (identity) – The local end's identity.
* RemoteIdentity (identity) – The remote end's identity.
* LocalEndpoint (object) – The local `exonet.Endpoint`.
* RemoteEndpoint (object) – The remote `exonet.Endpoint`.
* Outbound (bool) – True if the link was dialed by this node, false if accepted.
* Network (string8) – The transport network name (e.g. `tcp`, `tor`).
* HighPressure (bool) – True if the link is currently under back-pressure.
* BytesThroughput (uint64) – Current measured throughput in bytes per second.

## Example

```json
{
  "Type": "mod.nodes.link_info",
  "Object": {
    "ID": "7c1a93b50f2e4d18",
    "LocalIdentity": "02bef8840eb35ef2ae3c83c07cb5779278904f99cb4103f71e37cc69931ae5e15f",
    "RemoteIdentity": "037f990e61acee8a7697966afd29dd88f3b1f8a7b14d625c4f8742bd952003a590",
    "LocalEndpoint": {
      "Type": "tcp.endpoint",
      "Object": "10.0.0.5:1791"
    },
    "RemoteEndpoint": {
      "Type": "tcp.endpoint",
      "Object": "1.2.3.4:1791"
    },
    "Outbound": true,
    "Network": "tcp",
    "HighPressure": false,
    "BytesThroughput": 1024
  }
}
```
