# astrald.mod.fs.events.file_added

Emitted when a new file is detected in a watched repository.

## Fields

* Path (string16) – Filesystem path of the added file.
* ObjectID (object_id.sha256) – Object ID assigned to the new file.

## Example

```json
{
  "Type": "astrald.mod.fs.events.file_added",
  "Object": {
    "Path": "/data/myrepo/photo.jpg",
    "ObjectID": "data1ybnmhilrpghbrbsqhbsqhbsqhbsqhbsqhbsqhbsqhbsqhbsqhbsqha"
  }
}
```
