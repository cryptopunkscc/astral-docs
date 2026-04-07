# lna.channel_state_stats

A structure containing 24-hour aggregated statistics for one direction of a Lightning channel.

## Fields

* ShortChannelID (string) – The ID of the lightning channel.
* Source (identity) – The identity of the node on the source side of this direction.
* Direction (int64) – Direction of the channel (0 or 1).
* Capacity (uint64) – Most recent capacity of the channel in millisatoshis.
* AvgBase (float64) – Average base fee in millisatoshis over the last 24 hours.
* AvgRate (float64) – Average fee rate in parts per million over the last 24 hours.
* UpdateCount (int64) – Number of policy updates recorded in the last 24 hours.

## Example

```json
{
  "Type": "lna.channel_state_stats",
  "Object": {
    "ShortChannelID": "942555x660x0",
    "Source": "02bef8840eb35ef2ae3c83c07cb5779278904f99cb4103f71e37cc69931ae5e15f",
    "Direction": 0,
    "Capacity": 4000000000,
    "AvgBase": 1.0,
    "AvgRate": 5900.0,
    "UpdateCount": 3
  }
}
```
