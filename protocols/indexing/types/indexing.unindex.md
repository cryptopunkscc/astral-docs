# indexing.unindex

Notifies an indexer that an object has been removed from a repository.

## Fields

* Repo (string8) – Name of the repository the object was removed from.
* Version (uint64) – Monotonically increasing version number for this change.
* ObjectID (object_id.sha256) – Identifier of the removed object.

## Example

```json
{
  "Type": "indexing.unindex",
  "Object": {
    "Repo": "myrepo",
    "Version": 2,
    "ObjectID": "data1aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
  }
}
```
