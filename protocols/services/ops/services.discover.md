# services.discover

Stream service availability updates visible to the caller. Each `services.update` object describes a service becoming available or unavailable. In follow mode the channel stays open and delivers updates as they occur; otherwise the initial snapshot is sent followed by an `eos` object.

## Arguments

* follow (bool) – If true, keep the channel open and stream updates as they occur. Defaults to false.
* in (string8) – Input format.
* out (string8) – Output format.

## Returned objects

The operation returns one of:
* An `error_message` object if discovery cannot start.
* A stream of `services.update` objects followed by an `eos` object (or kept open when `follow` is true).

## Examples

```shellsession
$ astral-query services.discover -out json
{"Type":"services.update","Object":{"Available":true,"Name":"objects","ProviderID":"02bef8840eb35ef2ae3c83c07cb5779278904f99cb4103f71e37cc69931ae5e15f","Info":null}}
{"Type":"eos","Object":null}
```
