# services.update

Describes the availability of a named service, including which provider currently exposes it.

## Fields

* Available (bool) – True if the service is currently available, false if it has been withdrawn.
* Name (string8) – The service name.
* ProviderID (identity) – The identity of the node that provides the service.
* Info (object) – A `bundle` of supplementary objects attached by the provider; may be empty.

## Example

```json
{
  "Type": "services.update",
  "Object": {
    "Available": true,
    "Name": "chat",
    "ProviderID": "02bef8840eb35ef2ae3c83c07cb5779278904f99cb4103f71e37cc69931ae5e15f",
    "Info": []
  }
}
```
