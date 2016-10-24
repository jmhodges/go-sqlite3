load("@io_bazel_rules_go//go:def.bzl", "go_prefix", "go_library", "go_test", "cgo_library")

go_prefix("github.com/mattn/go-sqlite3")

cgo_library(
    name = "cgo_default_library",
    srcs = [
        "backup.go",
        "callback.go",
        "doc.go",
        "error.go",
        "sqlite3.go",
        "sqlite3-binding.c",
        "sqlite3-binding.h",
        "sqlite3_load_extension.go",
        "sqlite3_other.go",
        "sqlite3ext.h",
    ],
    visibility = ["//visibility:private"],
)

go_library(
    name = "go_default_library",
    srcs = ["tracecallback_noimpl.go"],
    library = ":cgo_default_library",
    visibility = ["//visibility:public"],
)

go_test(
    name = "go_default_test",
    srcs = [
        "backup_test.go",
        "callback_test.go",
        "error_test.go",
        "sqlite3_fts3_test.go",
        "sqlite3_test.go",
    ],
    library = ":go_default_library",
    deps = ["//sqlite3_test:go_default_library"],
)
