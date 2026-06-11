# astrald.mod.fs.events.file_changed

Emitted when a tracked file's content changes, carrying the old and new object IDs.

## Fields

* Path (string16) – Filesystem path of the changed file.
* OldID (object_id.sha256) – Object ID of the file before the change.
* NewID (object_id.sha256) – Object ID of the file after the change.

## Example

```json
{
  "Type": "astrald.mod.fs.events.file_changed",
  "Object": {
    "Path": "/data/myrepo/document.pdf",
    "OldID": "data1ybnmhilrpghbrbsqhbsqhbsqhbsqhbsqhbsqhbsqhbsqhbsqhbsqha",
    "NewID": "data1ypppqilrpghbrbsqhbsqhbsqhbsqhbsqhbsqhbsqhbsqhbsqhbsqhb"
  }
}
```
