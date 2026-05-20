# lna.channel_party_policy

A structure containing routing policy information for a Lightning Channel party.

## Fields

* NodeID (identity) – Identity of the channel party that set the policy.
* Active (bool) – Indicates whether the channel is active and available for routing.
* Delay (uint16) – The time-lock delta required for routing through the channel.
* FeeBase (uint64) – Base fee for routing through the channel in millisatoshis.
* FeeRate (uint64) – Proportional fee for routing a transaction through the channel in 1/1000000th units.
* LastUpdate (time) – The timestamp of the last channel policy update.
* Max (uint64) – Maximum HTLC value in millisatoshis that can be routed through the channel.
* Min (uint64) – Minimum HTLC value in millisatoshis that can be routed through the channel.

## Example

```json
{
  "Type": "lna.channel_party_policy",
  "Object": {
    "Active": true,
    "Delay": 34,
    "FeeBase": 0,
    "FeeRate": 0,
    "LastUpdate": "2026-04-02T18:01:07+02:00",
    "Max": 5940000000,
    "Min": 1,
    "NodeID": "02bef8840eb35ef2ae3c83c07cb5779278904f99cb4103f71e37cc69931ae5e15f"
  }
}
```
