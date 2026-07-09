# objects.get_blueprint

Return the [blueprint](../../../topics/blueprints.md) — the runtime wire-structure
schema — for a single type name. The blueprint describes only the named type;
referenced types are not resolved or included, so the caller fetches each
referenced type itself. The operation returns an `error_message` if the named
type is primitive (primitives have no blueprint) or is unknown.

## Arguments

* type (string8, required) – The type name to return the blueprint for.
* out (string8) – Output format.

## Returned objects

The operation returns one of:
* An `error_message` object if the named type is primitive (has no blueprint) or is unknown.
* The blueprint object for the named type.

## Examples

```shellsession
$ astral-query objects.get_blueprint -type mod.gateway.endpoint -out json
{"Type":"astral.Blueprint","Object":{"Kind":"struct","Name":"mod.gateway.endpoint","Fields":[{"Name":"GatewayID","Spec":{"Primitive":"identity"}},{"Name":"TargetID","Spec":{"Primitive":"identity"}}]}}
```
