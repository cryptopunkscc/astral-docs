# objects.type_spec

Field-level description of a registered astral struct type, produced by `objects.spec` for tools that build queries or forms dynamically.

## Fields

* Name (string8) – The astral type name (e.g. `mod.objects.probe`).
* Fields ([]field_spec) – One entry per inspectable struct field, each with `Name` (string), `Type` (string), and `Required` (bool).

## Example

```json
{
  "Type": "objects.type_spec",
  "Object": {
    "Name": "mod.objects.repository_info",
    "Fields": [
      {"Name": "Name", "Type": "string8", "Required": true},
      {"Name": "Label", "Type": "string8", "Required": true},
      {"Name": "Free", "Type": "int64", "Required": true}
    ]
  }
}
```
