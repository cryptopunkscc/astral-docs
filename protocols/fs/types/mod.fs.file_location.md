# mod.fs.file_location

Identifies a file by its hosting node and its filesystem path.

## Fields

* NodeID (identity) – Identity of the node that holds the file.
* Path (string16) – Absolute path to the file on that node's filesystem.

The text form is `<NodeID>:<Path>`.

## Example

```json
{
  "Type": "mod.fs.file_location",
  "Object": {
    "NodeID": "02bef8840eb35ef2ae3c83c07cb5779278904f99cb4103f71e37cc69931ae5e15f",
    "Path": "/data/myrepo/document.pdf"
  }
}
```
