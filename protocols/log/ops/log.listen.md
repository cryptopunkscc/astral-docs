# log.listen

Subscribe to the node's live log stream. The operation streams `astrald.log.entry` objects to the caller as log entries are produced; the stream runs until the caller disconnects.

## Returned objects

The operation returns a continuous stream of `astrald.log.entry` objects. The stream has no server-side terminator; it ends when the caller closes the connection.

## Examples

```shellsession
$ astral-query log.listen -out json
{"Type":"astrald.log.entry","Object":{"Origin":"02bef8840eb35ef2ae3c83c07cb5779278904f99cb4103f71e37cc69931ae5e15f","Level":1,"Time":"2026-06-10T12:00:00Z","Objects":[{"Type":"astrald.log.tag","Object":"net"},{"Type":"string8","Object":"link established"}]}}
{"Type":"astrald.log.entry","Object":{"Origin":"02bef8840eb35ef2ae3c83c07cb5779278904f99cb4103f71e37cc69931ae5e15f","Level":2,"Time":"2026-06-10T12:00:01Z","Objects":[{"Type":"astrald.log.tag","Object":"dir"},{"Type":"string8","Object":"resolved identity"}]}}
```
