# gateway.node_list

Stream the identities of all publicly registered nodes. Nodes registered with `"private"` visibility are excluded from the stream.

## Arguments

No arguments.

## Returned objects

The operation returns one of:
* One `identity` object per publicly registered node.
* An `eos` object terminating the stream.

## Examples

```shellsession
$ astral-query gateway.node_list -out json
{"Type":"identity","Object":"02bef8840eb35ef2ae3c83c07cb5779278904f99cb4103f71e37cc69931ae5e15f"}
{"Type":"identity","Object":"037f990e61acee8a7697966afd29dd88f3b1f8a7b14d625c4f8742bd952003a590"}
{"Type":"eos","Object":{}}
```
