# mod.apphost.bind_msg

A structure sent on an `apphost.bind` channel to bind the lifetime of
registered IPC handlers to the session. When the session closes, all handlers
that share the given token are removed.

## Fields

* Token (nonce64) – The token used when handlers were registered via `apphost.register_handler`.

## Example

```json
{
  "Type": "mod.apphost.bind_msg",
  "Object": {
    "Token": "a3f1c2d4e5b6f708"
  }
}
```
