# mod.ip.events.network_address_changed

Emitted when the set of local network interface addresses changes.

## Fields

* Removed ([]mod.ip.ip_address) – Addresses no longer present after the change.
* Added ([]mod.ip.ip_address) – Addresses newly present after the change.
* All ([]mod.ip.ip_address) – Complete set of local interface addresses after the change.

## Example

```json
{
  "Type": "mod.ip.events.network_address_changed",
  "Object": {
    "Removed": [],
    "Added": ["10.0.0.7"],
    "All": ["192.168.1.42", "10.0.0.7"]
  }
}
```
