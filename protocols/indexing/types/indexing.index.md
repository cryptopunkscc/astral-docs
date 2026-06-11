# indexing.index

Notifies an indexer that an object has been added to a repository.

## Fields

* Repo (string8) – Name of the repository the object was added to.
* Version (uint64) – Monotonically increasing version number for this change.
* ObjectID (object_id.sha256) – Identifier of the added object.

## Example

```json
{
  "Type": "indexing.index",
  "Object": {
    "Repo": "myrepo",
    "Version": 1,
    "ObjectID": "data1aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
  }
}
```
