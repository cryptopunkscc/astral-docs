# Batch mode

[Ops](../core-definitions/op.md) supports one or both of:
  - single mode — runs once, input via args, sends one result/error back
  - batch mode — reads objects from the channel until EOS/EOF, runs the op
   for each, sends the resuly/error per input, EOS at the end.
