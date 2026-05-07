# The Astral Knowledge Base

This documentation describes what the Astral Network is and how to interact 
with it.

* Fundamental Required Knowledge
  * [Core concepts](core-concepts/README.md) – architecture overview
    * [Alias](core-concepts/alias.md)
    * [App](core-concepts/app.md)
    * [Binary Encoding](core-concepts/binary-encoding.md)
    * [Channel](core-concepts/channel.md)
    * [Exonet](core-concepts/exonet.md)
    * [Identity](core-concepts/identity.md)
    * [JSON Encoding](core-concepts/json-encoding.md)
    * [Link](core-concepts/link.md)
    * [Local Swarm](core-concepts/local-swarm.md)
    * [Node](core-concepts/node.md)
    * [Object](core-concepts/object.md)
    * [Object ID](core-concepts/object-id.md)
    * [Object Stream](core-concepts/object-stream.md)
    * [Object Type](core-concepts/object-type.md)
    * [Op (Operation)](core-concepts/op.md)
    * [Protocol](core-concepts/protocol.md)
    * [Query](core-concepts/query.md)
    * [Query String](core-concepts/query-string.md)
    * [Stamp](core-concepts/stamp.md)
    * [Structure](core-concepts/structure.md)
    * [Swarm](core-concepts/swarm.md)
    * [Text Encoding](core-concepts/text-encoding.md)
    * [User](core-concepts/user.md)
  * [Common types](common-types/README.md) – common object types
    * [ack](common-types/ack.md)
    * [bool](common-types/bool.md)
    * [eos](common-types/eos.md)
    * [error_message](common-types/error_message.md)
    * [identity](common-types/identity.md)
    * [int8](common-types/int8.md)
    * [int16](common-types/int16.md)
    * [int32](common-types/int32.md)
    * [int64](common-types/int64.md)
    * [nonce64](common-types/nonce64.md)
    * [object](common-types/object.md)
    * [object_id.sha256](common-types/object_id.sha256.md)
    * [string8](common-types/string8.md)
    * [string16](common-types/string16.md)
    * [string32](common-types/string32.md)
    * [string64](common-types/string64.md)
    * [time](common-types/time.md)
    * [uint8](common-types/uint8.md)
    * [uint16](common-types/uint16.md)
    * [uint32](common-types/uint32.md)
    * [uint64](common-types/uint64.md)
* Protocol Definitions
  * [Basics](protocols/README.md) – protocol fundamentals
  * [dir](protocols/dir.md) - alias management, identity resolution
  * [lna](protocols/lna.md) - lightning network analytics
  * [tree](protocols/tree/README.md) - hierarchical key-value configuration store
* [Tools](tools/README.md) – command-line tools
  * [astral-query](tools/astral-query.md) - send queries from the command line
* Transports – how to access the local `Node`
  * [HTTP Transport](transports/http.md)

## Hints

* When editing protocol documentation, read [this](./protocols/README.md) first.