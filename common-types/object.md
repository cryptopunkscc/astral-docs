# object

* `object` is a generic type that can store any `Typed Object`.

## Binary Encoding

The object type encoded as string8 followed by the object payload.

For example a [`uint8`](uint8.md) of 21 is encoded as:

05 75 69 6e 74 38 15

## JSON Encoding

Encoded using the standard container from [JSON Encoding](../core-concepts/json-encoding.md):

```json
{
  "Type": "uint8",
  "Object": 21
}
```

## Text Encoding

Encoded using the standard [Text Encoding](../core-concepts/text-encoding.md)

```text
#[uint8] 21
```