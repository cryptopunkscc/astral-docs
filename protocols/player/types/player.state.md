# player.state

A snapshot of the playback state. While `Status` is "playing", the current position is extrapolated by observers as `Position + (now - UpdatedAt)`; the player emits a new snapshot on every transition rather than streaming continuous position updates.

The snapshot carries the current track's basic metadata (title, artist, album, cover art), extracted from the media file by the player, so front-ends never have to parse media formats themselves.

## Fields

* Status (string8) – One of "playing", "paused" or "stopped".
* Index (int32) – Queue index of the current track, or -1 if no track is loaded.
* Track (object_id.sha256) – Object ID of the current track, or the zero object ID if no track is loaded.
* Title (string8) – Title of the current track, or an empty string if unknown.
* Artist (string8) – Artist of the current track, or an empty string if unknown.
* Album (string8) – Album of the current track, or an empty string if unknown.
* Cover (object_id.sha256) – Object ID of the track's cover image, or the zero object ID if none is available.
* Position (uint64) – Playback position in milliseconds at the time given by `UpdatedAt`.
* Duration (uint64) – Duration of the current track in milliseconds, or 0 if unknown.
* UpdatedAt (time) – When this snapshot was taken.
* Version (uint64) – The queue version this snapshot refers to (see [player.queue](player.queue.md)).

Metadata fields are filled on a best-effort basis from the media's tags (e.g. ID3, Vorbis comments, FLAC metadata); they may be empty while the track is still loading.

## Example

```json
{
  "Type": "player.state",
  "Object": {
    "Status": "playing",
    "Index": 2,
    "Track": "data1aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
    "Title": "Paranoid Android",
    "Artist": "Radiohead",
    "Album": "OK Computer",
    "Cover": "data1cccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccc",
    "Position": 73500,
    "Duration": 214000,
    "UpdatedAt": "2026-06-09T12:00:00Z",
    "Version": 17
  }
}
```
