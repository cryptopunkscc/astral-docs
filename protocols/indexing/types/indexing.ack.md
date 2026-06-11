# indexing.ack

Acknowledges receipt and successful processing of a single index change delivered by `indexing.subscribe`.

## Fields

* Repo (string8) – Name of the repository from the acknowledged change.
* Version (uint64) – Version number from the acknowledged change.

## Example

```json
{
  "Type": "indexing.ack",
  "Object": {
    "Repo": "myrepo",
    "Version": 1
  }
}
```
