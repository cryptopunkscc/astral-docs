# mod.objects.create_object_action

An `auth.action` payload requesting permission to create a new object in a repository. Embedded fields come from `auth.Action`.

## Fields

* Action (auth.action) – Embedded base action containing the caller identity and other auth metadata.

## Example

```json
{
  "Type": "mod.objects.create_object_action",
  "Object": {
    "Action": {
      "CallerID": "02bef8840eb35ef2ae3c83c07cb5779278904f99cb4103f71e37cc69931ae5e15f"
    }
  }
}
```
