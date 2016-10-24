load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_binary")

go_library(
    name = "go_default_library",
    srcs = ["upgrade.go"],
    visibility = ["//visibility:private"],
    deps = ["@com_github_PuerkitoBio_goquery//:go_default_library"],
)

go_binary(
    name = "tool",
    library = ":go_default_library",
    visibility = ["//visibility:public"],
    deps = ["go_default_library"],
)
