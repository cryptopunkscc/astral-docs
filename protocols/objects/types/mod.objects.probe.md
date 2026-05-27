# mod.objects.probe

The result of probing an object: its astral type (if any), MIME type, host repository, and read latency.

## Fields

* Type (string8) – The astral type name, or empty if the payload has no astral stamp.
* Repo (string8) – Name of the repository the object was found in.
* Mime (string8) – Detected MIME type of the first bytes (via Go's `http.DetectContentType`).
* Time (duration) – Time taken to fetch the probe sample, in nanoseconds.

## Example

```json
{
  "Type": "mod.objects.probe",
  "Object": {
    "Type": "string8",
    "Repo": "local",
    "Mime": "text/plain; charset=utf-8",
    "Time": 421000
  }
}
```
