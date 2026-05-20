# lna.channel

A structure containing information about a Lightning Channel.

## Fields

* ShortChannelID (string) – The ID of the lightning channel. 
* Amount (uint64) – Capacity of the channel in msat (millisats).
* Destination (identity) – The identity on the destination side of the channel.
* DestinationPolicy (lna.channel_policy) – The routing policy for the
  destination side.
* Source (identity) – The identity on the source side of the channel.
* SourcePolicy (lna.channel_policy) – The routing policy for the source side.

## Example

```json
{
  "Type": "lna.channel",
  "Object": {
    "Amount": 4000000000,
    "Destination": "03864ef025fde8fb587d989186ce6a4a186895ee44a926bfc370e2c366597a3f8f",
    "DestinationPolicy": {
      "Active": true,
      "Delay": 144,
      "FeeBase": 1000,
      "FeeRate": 499,
      "LastUpdate": "2026-04-05T00:56:33+02:00",
      "Max": 1800000000,
      "Min": 0
    },
    "ShortChannelID": "942555x660x0",
    "Source": "02bef8840eb35ef2ae3c83c07cb5779278904f99cb4103f71e37cc69931ae5e15f",
    "SourcePolicy": {
      "Active": true,
      "Delay": 34,
      "FeeBase": 1,
      "FeeRate": 5900,
      "LastUpdate": "2026-04-05T01:33:14+02:00",
      "Max": 1800000000,
      "Min": 1
    }
  }
}

```