# objects.query_tag

A single tag inside an `objects.search_query`. Tags can be required (`tag:value`), excluded (`-tag:value`), or optionally included/excluded (`?tag:value`, `~tag:value`).

## Fields

* Name (string8) – Tag name (lowercased on parse).
* Mod (string8) – Tag modifier; one of `""` (require), `"EXCLUDE"`, `"OPTIONAL"`, `"OPTIONAL_EXCLUDE"`.
* Value (string8) – Tag value (lowercased on parse).

## Example

```json
{
  "Type": "objects.query_tag",
  "Object": {
    "Name": "mime",
    "Mod": "",
    "Value": "text/plain"
  }
}
```
