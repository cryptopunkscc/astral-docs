# mod.user.notification

A push notification sent between sibling nodes to signal that some user-owned
state has changed. Currently used with `Event = "assets"` after a node mutates
its asset list, asking siblings to pull the change via `user.sync_assets` or
`user.sync_with`.

## Fields

* Event (string8) – Name of the event. Defined: `"assets"`.

## Example

```json
{
  "Type": "mod.user.notification",
  "Object": { "Event": "assets" }
}
```
