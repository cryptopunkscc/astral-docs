# Structure

* A structured `Object` consists of other objects ordered and named (fields).
  Field names are used in JSON encoding, while binary encoding relies on the 
  order of fields and does not encode their names at all.
* For example a structure:
  * Name (string8)
  * IDs ([]uint16)
* 