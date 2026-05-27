# mod.objects.describe_result

A single descriptor produced by a describer for a given object. `objects.describe` streams one of these per descriptor.

## Fields

* SourceID (identity) – The identity of the describer that produced the descriptor.
* ObjectID (object_id.sha256) – The id of the object being described.
* Data (object) – The descriptor payload itself; any astral object type.

## Example

```json
{
  "Type": "mod.objects.describe_result",
  "Object": {
    "SourceID": "02bef8840eb35ef2ae3c83c07cb5779278904f99cb4103f71e37cc69931ae5e15f",
    "ObjectID": "data1aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
    "Data": {
      "Type": "string8",
      "Object": "hello"
    }
  }
}
```
