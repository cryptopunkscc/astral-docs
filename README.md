# The Astral Network

This documentation describes the Astral Network and how to interact with it.

* [Core primitives](core-primitives/README.md)
  * [Alias](core-primitives/alias.md)
  * [App](core-primitives/app.md)
  * [Channel](core-primitives/channel.md)
  * [Exonet](core-primitives/exonet.md)
  * [Identity](core-primitives/identity.md)
  * [Link](core-primitives/link.md)
  * [Local Swarm](core-primitives/local-swarm.md)
  * [Node](core-primitives/node.md)
  * [Object](core-primitives/object.md)
  * [Object ID](core-primitives/object-id.md)
  * [Object Stream](core-primitives/object-stream.md)
  * [Object Type](core-primitives/object-type.md)
  * [Op (Operation)](core-primitives/op.md)
  * [Protocol](core-primitives/protocol.md)
  * [Query](core-primitives/query.md)
  * [Query String](core-primitives/query-string.md)
  * [Stamp](core-primitives/stamp.md)
  * [Structure](core-primitives/structure.md)
  * [Swarm](core-primitives/swarm.md)
  * [User](core-primitives/user.md)
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
* Protocols
  * [Basics](protocols/README.md) – protocol documentation structure
  * [apphost](protocols/apphost/README.md) - on-device API for local apps (tokens, handlers, contracts, holds)
  * [bip137sig](protocols/bip137sig/README.md) - BIP-39/32/137 seed, key derivation, and message signing
  * [crypto](protocols/crypto/README.md) - signing and verifying hashes and text, public key derivation
  * [dir](protocols/dir/README.md) - alias management, identity resolution
  * [lna](protocols/lna/README.md) - lightning network analytics
  * [nodes](protocols/nodes/README.md) - encrypted links and multiplexed sessions between nodes
  * [objects](protocols/objects/README.md) - typed object storage, retrieval, and provider discovery
  * [tree](protocols/tree/README.md) - hierarchical key-value configuration store
  * [user](protocols/user/README.md) - user identity, swarm membership, asset list
* [Tools](tools/README.md) – command-line tools
  * [astral-query](tools/astral-query.md) - send queries from the command line
* Other topic
  * [Node Setup](topics/node-setup.md)
  * [Node Claiming](topics/node-claiming.md)
  * [HTTP Transport](topics/http-transport.md)
  * [Binary Encoding](topics/binary-encoding.md)
  * [JSON Encoding](topics/json-encoding.md)
  * [Text Encoding](topics/text-encoding.md)
