Demonstrates bug in scala-bazel rules.

Resources are only included in scala_library rules
if srcs is nonempty.

    /save/src/scala-bazel-bug ‹master*›  [2017-02-08 11:03:39]
    [0]$ bazel build //...
    INFO: Found 3 targets...
    INFO: From Building external/io_bazel_rules_scala/src/java/io/bazel/rulesscala/scalac/scalac.jar (2 source files) [for host]:
    Note: external/io_bazel_rules_scala/src/java/io/bazel/rulesscala/scalac/CompileOptions.java uses unchecked or unsafe operations.
    Note: Recompile with -Xlint:unchecked for details.
    INFO: Elapsed time: 11.917s, Critical Path: 7.00s
    ~/save/src/scala-bazel-bug ‹master*›  [2017-02-08 11:03:52]
    [0]$ cd bazel-bin/src
    ~/save/src/scala-bazel-bug/bazel-bin/src  [2017-02-08 11:03:57]
    [0]$ jar -tf with_srcs.jar | grep foo.txt
    foo.txt
    ~/save/src/scala-bazel-bug/bazel-bin/src  [2017-02-08 11:04:10]
    [0]$ jar -tf without_srcs.jar | grep foo.txt
    ~/save/src/scala-bazel-bug/bazel-bin/src  [2017-02-08 11:04:13]
    [1]$
