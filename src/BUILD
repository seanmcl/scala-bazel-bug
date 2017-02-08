load("@io_bazel_rules_scala//scala:scala.bzl", "scala_library", "scala_binary", "scala_test")

scala_library(
    name = "with_srcs",
    srcs = glob(["*.scala"]),
    resources = [
        "//resources:configs",
    ],
    visibility = ["//visibility:public"],
)

scala_library(
    name = "without_srcs",
    srcs = [],
    resources = [
        "//resources:configs",
    ],
    visibility = ["//visibility:public"],
)
