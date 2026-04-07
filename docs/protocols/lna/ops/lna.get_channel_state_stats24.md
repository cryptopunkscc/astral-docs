# lna.get_channel_state_stats24

Get 24-hour channel state statistics for all channels.

## Arguments

None.

## Return values

The method returns an object stream of `lna.channel_state_stats` objects, followed by `eos`.

## Examples

```shellsession
$ astral-query target:lna.get_channel_state_stats24 -out json
{"Type":"lna.channel_state_stats","Object":{"ShortChannelID":"942555x660x0","Source":"02bef8840eb35ef2ae3c83c07cb5779278904f99cb4103f71e37cc69931ae5e15f","Direction":0,"Capacity":4000000000,"AvgBase":1.0,"AvgRate":5900.0,"UpdateCount":3}}
{"Type":"lna.channel_state_stats","Object":{"ShortChannelID":"942564x704x0","Source":"026165850492521f4ac8abd9bd8088123446d126f648ca35e60f88177dc149ceb2","Direction":0,"Capacity":6000000000,"AvgBase":0.0,"AvgRate":1.0,"UpdateCount":1}}
{"Type":"eos","Object":null}
```
