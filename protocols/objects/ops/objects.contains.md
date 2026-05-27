# objects.contains

Check whether a repository might contain an object method nature is probabilistic.

## Arguments

* repo (string8, required) – Name of the repository to check.
* id (object_id.sha256) – The id to check for. If omitted, the operation streams ids from the input.
* in (string8) – Input format for streamed ids.
* out (string8) – Output format.
* (stream) – When `id` is omitted, a stream of `object_id.sha256` objects to check.

## Returned objects

The operation returns one of:
* An `error_message` object if the repository is not found or the lookup fails.
* A `bool` object for each id (one shot if `id` was given, otherwise one per streamed id).

## Examples

```shellsession
$ astral-query objects.contains -repo local -id data1aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa -out json
{"Type":"bool","Object":true}
```
