# player.state

Get the current playback state, including the current track's metadata (title, artist, album, cover image).

## Arguments

* follow (bool) – If true, stream a new state snapshot on every state change (the operation stays open).

## Returned objects

The operation returns one of:
* An `error_message` object if there was an error.
* A `player.state` object, followed by an `eos` object (or a stream of state snapshots if `follow` is true).

## Examples

```shellsession
$ astral-query player.state -out json
{"Type":"player.state","Object":{"Status":"playing","Index":2,"Track":"data1aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa","Title":"Paranoid Android","Artist":"Radiohead","Album":"OK Computer","Cover":"data1cccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccc","Position":73500,"Duration":214000,"UpdatedAt":"2026-06-09T12:00:00Z","Version":17}}
{"Type":"eos","Object":null}
```

```shellsession
$ astral-query player.state -follow true -out json
{"Type":"player.state","Object":{"Status":"playing","Index":2,"Track":"data1aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa","Title":"Paranoid Android","Artist":"Radiohead","Album":"OK Computer","Cover":"data1cccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccc","Position":73500,"Duration":214000,"UpdatedAt":"2026-06-09T12:00:00Z","Version":17}}
{"Type":"player.state","Object":{"Status":"paused","Index":2,"Track":"data1aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa","Title":"Paranoid Android","Artist":"Radiohead","Album":"OK Computer","Cover":"data1cccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccc","Position":80100,"Duration":214000,"UpdatedAt":"2026-06-09T12:00:06Z","Version":17}}
```
