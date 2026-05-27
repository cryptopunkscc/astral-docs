# mod.objects.repository_info

Summary information about a registered repository.

## Fields

* Name (string8) – Repository name as registered with the module (e.g. `local`, `mem0`).
* Label (string8) – Human-readable label describing the repository.
* Free (int64) – Free bytes available in the repository, or `-1` if not applicable (e.g. for repo groups).

## Example

```json
{
  "Type": "mod.objects.repository_info",
  "Object": {
    "Name": "local",
    "Label": "Local storage",
    "Free": 549755813888
  }
}
```
