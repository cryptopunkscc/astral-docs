# mod.objects.commit_msg

A zero-size sentinel that terminates a chunked write to `objects.create`. Receiving it commits the open writer and returns the resulting object id.

## Encoding

* Binary: empty (no bytes written or read).
* Text/JSON: an empty object.

## Example

```json
{
  "Type": "mod.objects.commit_msg",
  "Object": null
}
```
