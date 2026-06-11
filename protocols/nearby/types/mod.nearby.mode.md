# mod.nearby.mode

Controls how the node broadcasts its presence on the local network.

## Fields

`mod.nearby.mode` is a `uint8` alias. The value is one of:

* `0` – Silent: the node does not broadcast.
* `1` – Visible: the node broadcasts; content depends on the contract state.
* `2` – Stealth: the node broadcasts with a masked identity to hide the user–node association.

The default mode when a user identity is set is `2` (Stealth).

## Example

```json
{
  "Type": "mod.nearby.mode",
  "Object": 1
}
```
