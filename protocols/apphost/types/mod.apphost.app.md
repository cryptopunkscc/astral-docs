# mod.apphost.app

A structure describing a local app installed on the node.

## Fields

* AppID (identity) – The app's identity.
* HostID (identity) – The host node identity that installed the app.
* InstalledAt (time) – The instant the app was installed.

## Example

```json
{
  "Type": "mod.apphost.app",
  "Object": {
    "AppID": "0282fee8775757cdd8fda8b220195f5b8611312cd145c5a1a3aa55df210e779b2c",
    "HostID": "026165850492521f4ac8abd9bd8088123446d126f648ca35e60f88177dc149ceb2",
    "InstalledAt": "2026-05-27T12:00:00+02:00"
  }
}
```
