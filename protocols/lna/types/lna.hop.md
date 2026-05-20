# lna.hop

A structure containing information about a hop in a payment route.

## Fields

* ShortChannelID (string) – the short channel ID of the channel being used in this hop
* Destination (string) – the public key of the next node in the route
* Cost (uint64) – the cost of this hop in millisatoshis
* Delay (uint64) – the HTLC delays at this hop till the end of the route

## Examples

``json
{
  "Type": "lna.hop",
  "Object": {
    "Cost": 12,
    "Delay": 442,
    "Destination": "026165850492521f4ac8abd9bd8088123446d126f648ca35e60f88177dc149ceb2",
    "ShortChannelID": "942564x704x0"
  }
}
``