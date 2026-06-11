# routing.op_spec

Describes a single routable operation: its name and the parameters it accepts.

## Fields

* Name (string) – The operation name as used in query strings.
* Parameters ([]field_spec) – One entry per accepted parameter, each with `Name` (string), `Type` (string), and `Required` (bool).

## Example

```json
{
  "Type": "routing.op_spec",
  "Object": {
    "Name": "discover",
    "Parameters": [
      {"Name": "name", "Type": "string8", "Required": false}
    ]
  }
}
```
