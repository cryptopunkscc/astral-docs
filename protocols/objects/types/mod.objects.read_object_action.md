# mod.objects.read_object_action

An `auth.action` payload requesting permission to read a specific object. Used by `objects.read` to authorize the caller.

## Fields

* Action (auth.action) – Embedded base action containing the caller identity and other auth metadata.
* ObjectID (object_id.sha256) – The id of the object being requested.

## Example

```json
{
  "Type": "mod.objects.read_object_action",
  "Object": {
    "Action": {
      "CallerID": "02bef8840eb35ef2ae3c83c07cb5779278904f99cb4103f71e37cc69931ae5e15f"
    },
    "ObjectID": "data1aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
  }
}
```
