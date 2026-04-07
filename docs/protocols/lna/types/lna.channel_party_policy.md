# lna.channel_party_policy

This object contains information about a Lightning Channel routing policy.

## Payload fields

| Name       | Type     | Description                                                                          |
|------------|----------|--------------------------------------------------------------------------------------|
| NodeID     | identity | Idenitty of the channel party that set the policy                                    |
| Active     | bool     | Indicates whether the channel is active and available for routing.                   |
| Delay      | uint16   | The time-lock delta required for routing through the channel.                        |
| FeeBase    | uint64   | Base fee for routing through the channel in millisatoshis.                           |
| FeeRate    | uint64   | Proportional fee for routing a transaction through the channel in 1/1000000th units. |
| LastUpdate | time     | The timestamp of the last update of the channel policy.                              |
| Max        | uint64   | Maximum HTLC value in millisatoshis that can be routed through the channel.          |
| Min        | uint64   | Minimum HTLC value in millisatoshis that can be routed through the channel.          |
