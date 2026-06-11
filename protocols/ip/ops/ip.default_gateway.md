# ip.default_gateway

Return the IP address of the default network gateway.

## Arguments

None.

## Returned objects

The operation returns one of:
* An `error_message` object if the default gateway cannot be determined.
* A `mod.ip.ip_address` object containing the gateway address.

## Examples

```shellsession
$ astral-query ip.default_gateway -out json
{"Type":"mod.ip.ip_address","Object":"192.168.1.1"}
```
