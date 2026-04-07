# lna.channel_state_stats

This object contains 24-hour aggregated statistics for one direction of a Lightning channel.

## Payload fields

| Name           | Type     | Description                                                            |
|----------------|----------|------------------------------------------------------------------------|
| ShortChannelID | string   | The ID of the lightning channel.                                       |
| Source         | identity | The identity of the node on the source side of this direction.         |
| Direction      | int64    | Direction of the channel (0 or 1).                                     |
| Capacity       | uint64   | Most recent capacity of the channel in millisatoshis.                  |
| AvgBase        | float64  | Average base fee in millisatoshis over the last 24 hours.              |
| AvgRate        | float64  | Average fee rate in parts per million over the last 24 hours.          |
| UpdateCount    | int64    | Number of policy updates recorded in the last 24 hours.                |
