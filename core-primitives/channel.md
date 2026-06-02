# Channel

* A `Channel` is used to exchange `Objects` between two parties.
* A `Channel` can be closed by either party at any time.
* A `Channel` uses the `Binary Encoding` by default.
* A `Channel` can use any encoding as long as both parties support it. For
  example, an `Operation` can take `Operation Parameters` to specify the
  encoding.

## Binary Encoding

Objects are sent over the channel by writing their type encoded as `string8` 
followed by their payload encoded as `bytes32`. An empty type means a binary
untyped blob.

```
String8(ObjectType) ++ Bytes32(Payload)`
```
