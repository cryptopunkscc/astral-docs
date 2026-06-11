# fs.new_repo

Register a new filesystem repository backed by a directory at the given path. The repository is added to the `objects.RepoLocal` group under the given name, and the label defaults to the name when omitted.

## Arguments

* path (string, required) – Absolute filesystem path to the directory that backs the repository.
* name (string, required) – Name used to register the repository with the objects module.
* label (string) – Human-readable label for the repository. Defaults to the value of `name`.

## Returned objects

The operation returns one of:
* An `error_message` object if repository registration fails or the group assignment fails.
* An `ack` object on success.

## Examples

```shellsession
$ astral-query fs.new_repo -path /data/myrepo -name myrepo -out json
{"Type":"ack","Object":{}}
```
