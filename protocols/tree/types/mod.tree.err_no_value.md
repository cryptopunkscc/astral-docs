# mod.tree.err_no_value

The error object returned by the [`tree`](../README.md) protocol when a path
exists but holds no value. It is distinct from a missing-path error: the node
addressed by the path is present, it simply has no value set. A read such as
`tree.get` surfaces this object in place of a stored value.

## Fields

This error carries no fields.

## Example

```json
{
  "Type": "mod.tree.err_no_value",
  "Object": null
}
```
