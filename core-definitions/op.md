# Op (Operation)

* An `Op` is a single API method that has an `Op Name` and a
  set of `Op Parameters`.
* An `Op Name` consists of alphanumeric characters, periods and 
  underscores, starting with a letter. Period is conventionally used to for 
  namespacing.
* An `Op Parameter` has a `Parameter Name` and an [`Object Type`](object-type.md) it takes.
* Only `Object Types` that support type-specific [`Text Encoding`](../topics/text-encoding.md) can be used as
  `Op Parameters`.
* When run over an accepted [`Query`](query.md)'s [`Channel`](channel.md), an `Op`
  reads input [`Objects`](object.md) and writes result `Objects` back. It runs in
  single or batch mode, and single-mode `Ops` compose into pipelines — see
  [Op modes & composition](../topics/op-modes.md).
