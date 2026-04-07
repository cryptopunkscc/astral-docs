# lna.channel_policy

A structure containing routing policy information for one side of a Lightning Channel.

## Fields

* Active (bool) – Indicates whether the channel is active and available for routing.
* Delay (uint16) – The time-lock delta required for routing through the channel.
* FeeBase (uint64) – Base fee for routing through the channel in millisatoshis.
* FeeRate (uint64) – Proportional fee for routing a transaction through the channel in 1/1000000th units.
* LastUpdate (time) – The timestamp of the last update of the channel policy.
* Max (uint64) – Maximum HTLC value in millisatoshis that can be routed through the channel.
* Min (uint64) – Minimum HTLC value in millisatoshis that can be routed through the channel.

## Example

```json
{
  "Type": "lna.channel_policy",
  "Object": {
    "Active": true,
    "Delay": 34,
    "FeeBase": 1,
    "FeeRate": 5900,
    "LastUpdate": "2026-04-05T01:33:14+02:00",
    "Max": 1800000000,
    "Min": 1
  }
}
```
