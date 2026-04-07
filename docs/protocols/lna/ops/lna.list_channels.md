# lna.list_channels

Get a list of channels.

## Arguments

| Name | Type     | Description                                        |
| ---- | -------- |----------------------------------------------------|
| id   | identity | List channels where one of the parties has this ID |

## Return values

The method returns an object stream of `lna.channel` objects.

## Examples

```shellsession
$ astral-query target:lna.list_channels -id 02bef8840eb35ef2ae3c83c07cb5779278904f99cb4103f71e37cc69931ae5e15f -out json
{"Type":"lna.channel","Object":{"Amount":4000000000,"Destination":"03864ef025fde8fb587d989186ce6a4a186895ee44a926bfc370e2c366597a3f8f","DestinationPolicy":{"Active":true,"Delay":144,"FeeBase":1000,"FeeRate":499,"LastUpdate":"2026-04-05T00:56:33+02:00","Max":1800000000,"Min":0},"ShortChannelID":"942555x660x0","Source":"02bef8840eb35ef2ae3c83c07cb5779278904f99cb4103f71e37cc69931ae5e15f","SourcePolicy":{"Active":true,"Delay":34,"FeeBase":1,"FeeRate":5900,"LastUpdate":"2026-04-05T01:33:14+02:00","Max":1800000000,"Min":1}}}
{"Type":"lna.channel","Object":{"Amount":6000000000,"Destination":"026165850492521f4ac8abd9bd8088123446d126f648ca35e60f88177dc149ceb2","DestinationPolicy":{"Active":true,"Delay":80,"FeeBase":0,"FeeRate":1,"LastUpdate":"2026-04-07T01:40:49+02:00","Max":6000000000,"Min":1000},"ShortChannelID":"942564x704x0","Source":"02bef8840eb35ef2ae3c83c07cb5779278904f99cb4103f71e37cc69931ae5e15f","SourcePolicy":{"Active":true,"Delay":34,"FeeBase":0,"FeeRate":1,"LastUpdate":"2026-04-05T01:33:42+02:00","Max":5940000000,"Min":1}}}
{"Type":"eos","Object":null}
```
