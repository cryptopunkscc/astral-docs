# lna.channel

This object contains information about a Lightning Channel.

## Payload fields

| Name              | Type               | Description                                          |
|-------------------|--------------------|------------------------------------------------------|
| ShortChannelID    | string             | The ID of the lightning channel.                     |
| Amount            | uint64             | Capacity of the channel in millisatoshis.            |
| Destination       | identity           | The identity on the destination side of the channel. |
| DestinationPolicy | lna.channel_policy | The routing policy for the destination side.         |
| Source            | identity           | The identity on the source side of the channel.      |
| SourcePolicy      | lna.channel_policy | The routing policy for the source side.              |

