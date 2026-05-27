# mod.objects.search_result

A single match produced by a searcher. `objects.search` streams one of these per deduplicated hit.

## Fields

* SourceID (identity) – The identity of the searcher that produced the match.
* ObjectID (object_id.sha256) – The id of the matching object.

## Example

```json
{
  "Type": "mod.objects.search_result",
  "Object": {
    "SourceID": "02bef8840eb35ef2ae3c83c07cb5779278904f99cb4103f71e37cc69931ae5e15f",
    "ObjectID": "data1aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
  }
}
```
