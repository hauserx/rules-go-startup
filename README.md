Build times for rules\_go builds with already fetched external deps.

Results for:

bazel: 6.5
rules\_go: 0.46
go: 1.22.0

## Linux

```
bazel clean
bazel build :hello

INFO: Elapsed time: 16.011s, Critical Path: 15.35s
INFO: 12 processes: 7 internal, 5 linux-sandbox.
INFO: Build completed successfully, 12 total actions

~7 seconds (2x in parallel) GoToolchainBinaryBuild external/go_sdk/builder
~7 seconds                  GoStdlib external/io_bazel_rules_go/stdlib_/pkg
```


## Windows

```

bazel clean
bazel build :hello

INFO: Elapsed time: 66.412s, Critical Path: 64.35s
INFO: 14 processes: 9 internal, 5 local.
INFO: Build completed successfully, 14 total actions

~25 seconds (2x in parallel) GoToolchainBinaryBuild external/go_sdk/builder.exe
~35 seconds                  GoStdlib external/io_bazel_rules_go/stdlib_/pkg
```
