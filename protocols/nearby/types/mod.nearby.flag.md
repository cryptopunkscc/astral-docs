# mod.nearby.flag

A single string tag attached to a nearby node's status.

## Fields

`mod.nearby.flag` has no struct fields. The type is a named `string8` alias; the entire value is the flag string.

The text form is the flag string itself; JSON encodes the value as a plain string.

## Example

```json
{
  "Type": "mod.nearby.flag",
  "Object": "online"
}
```
