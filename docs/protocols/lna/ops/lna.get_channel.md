# lna.get_channel

Get channel info.

## Arguments

| Name | Type   | Description       |
| ---- | ------ | ----------------- |
| id   | string | ID of the channel |

## Return values

The method returns a `lna.channel` object.

## Examples

```shellsession
$ astral-query target:lna.get_channel -id 942564x704x0 -out json
{"Type":"lna.channel","Object":{"Amount":6000000000,"Destination":"02bef8840eb35ef2ae3c83c07cb5779278904f99cb4103f71e37cc69931ae5e15f","DestinationPolicy":{"Active":true,"Delay":34,"FeeBase":0,"FeeRate":0,"LastUpdate":"2026-04-02T18:01:07+02:00","Max":5940000000,"Min":1},"ShortChannelID":"942564x704x0","Source":"026165850492521f4ac8abd9bd8088123446d126f648ca35e60f88177dc149ceb2","SourcePolicy":{"Active":true,"Delay":80,"FeeBase":0,"FeeRate":1,"LastUpdate":"2026-04-02T11:09:29+02:00","Max":6000000000,"Min":1000}}}
```
