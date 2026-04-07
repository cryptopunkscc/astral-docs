# lna.get_node

Get node info.

## Arguments

| Name | Type     | Description          |
| ---- |----------|----------------------|
| id   | identity | ID of the node       |

## Return values

The method returns a `lna.node` object.

## Examples

```shellsession
$ astral-query target:lna.get_node -id 02bef8840eb35ef2ae3c83c07cb5779278904f99cb4103f71e37cc69931ae5e15f -out json
{"Type":"lna.node","Object":{"Alias":"void0","Color":"02bef8","CustomAlias":"cln","Features":"808898880a8a59a1","Identity":"02bef8840eb35ef2ae3c83c07cb5779278904f99cb4103f71e37cc69931ae5e15f","LastTimestamp":1774881178}}
```
