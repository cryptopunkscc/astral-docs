# Protocols

* Subdirectories in this directory are named after protocols they describe.
* The `Object Types` used by protocols are described in their "types" subdirectory.
* The `Operations` used by protocols are described in their "ops" subdirectory.
* All operations implicitly support the special "in" and "out" parameters. 
  Those parameters are used to specify the input and output encoding for the 
  operation and can be one of "bin", "json" and "text".