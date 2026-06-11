# coldcard.scan

Scan for connected Coldcard hardware wallets and update the module's device state.

## Arguments

* in (string8) – Input format.
* out (string8) – Output format.

## Returned objects

The operation returns one of:
* An `error_message` object if the scan fails.
* An `ack` object on success.

## Examples

```shellsession
$ astral-query coldcard.scan -out json
{"Type":"ack","Object":null}
```
