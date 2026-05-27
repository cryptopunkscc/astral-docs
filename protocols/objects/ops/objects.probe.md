# objects.probe

Probe an object to determine its astral type, MIME type, host repository, and read latency.

## Arguments

* id (object_id.sha256) – Id to probe. If omitted, the operation streams ids from the input.
* repo (string8) – Repository to probe in. Defaults to the read-default repository.
* in (string8) – Input format.
* out (string8) – Output format.
* (stream) – When `id` is omitted, a stream of `object_id.sha256` objects to probe; `eos` closes the channel.

## Returned objects

The operation returns one of:
* An `error_message` object if the repository is not found or the probe fails.
* A `mod.objects.probe` object for each id (one shot if `id` was given, otherwise one per streamed id).

## Examples

```shellsession
$ astral-query objects.probe -id data1aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa -out json
{"Type":"mod.objects.probe","Object":{"Type":"string8","Repo":"local","Mime":"text/plain; charset=utf-8","Time":421000}}
```
