load("@io_bazel_rules_go//go:def.bzl", "go_library")

go_library(
    name = "go_default_library",
    srcs = [
        "backup.go",
        "callback.go",
        "doc.go",
        "error.go",
        "sqlite3.go",
        "sqlite3-binding.c",
        "sqlite3-binding.h",
        "sqlite3_load_extension.go",
        "sqlite3ext.h",
    ] + select({
        "@io_bazel_rules_go//go/platform:android": [
            "sqlite3_other.go",
        ],
        "@io_bazel_rules_go//go/platform:darwin": [
            "sqlite3_other.go",
        ],
        "@io_bazel_rules_go//go/platform:dragonfly": [
            "sqlite3_other.go",
        ],
        "@io_bazel_rules_go//go/platform:freebsd": [
            "sqlite3_other.go",
        ],
        "@io_bazel_rules_go//go/platform:linux": [
            "sqlite3_other.go",
        ],
        "@io_bazel_rules_go//go/platform:nacl": [
            "sqlite3_other.go",
        ],
        "@io_bazel_rules_go//go/platform:netbsd": [
            "sqlite3_other.go",
        ],
        "@io_bazel_rules_go//go/platform:openbsd": [
            "sqlite3_other.go",
        ],
        "@io_bazel_rules_go//go/platform:plan9": [
            "sqlite3_other.go",
        ],
        "@io_bazel_rules_go//go/platform:solaris": [
            "sqlite3_other.go",
        ],
        "@io_bazel_rules_go//go/platform:windows": [
            "sqlite3_windows.go",
        ],
        "//conditions:default": [],
    }),
    cgo = True,
    clinkopts = select({
        "@io_bazel_rules_go//go/platform:linux": [
            "-ldl",
        ],
        "@io_bazel_rules_go//go/platform:windows": [
            "-lmingwex -lmingw32",
        ],
        "//conditions:default": [],
    }),
    copts = [
        "-std=gnu99",
        "-DSQLITE_ENABLE_RTREE -DSQLITE_THREADSAFE",
        "-DSQLITE_ENABLE_FTS3 -DSQLITE_ENABLE_FTS3_PARENTHESIS -DSQLITE_ENABLE_FTS4_UNICODE61",
    ] + select({
        "@io_bazel_rules_go//go/platform:android": [
            "-Ivendor/github.com/mattn/go-sqlite3",
        ],
        "@io_bazel_rules_go//go/platform:darwin": [
            "-Ivendor/github.com/mattn/go-sqlite3",
        ],
        "@io_bazel_rules_go//go/platform:dragonfly": [
            "-Ivendor/github.com/mattn/go-sqlite3",
        ],
        "@io_bazel_rules_go//go/platform:freebsd": [
            "-Ivendor/github.com/mattn/go-sqlite3",
        ],
        "@io_bazel_rules_go//go/platform:linux": [
            "-Ivendor/github.com/mattn/go-sqlite3",
        ],
        "@io_bazel_rules_go//go/platform:nacl": [
            "-Ivendor/github.com/mattn/go-sqlite3",
        ],
        "@io_bazel_rules_go//go/platform:netbsd": [
            "-Ivendor/github.com/mattn/go-sqlite3",
        ],
        "@io_bazel_rules_go//go/platform:openbsd": [
            "-Ivendor/github.com/mattn/go-sqlite3",
        ],
        "@io_bazel_rules_go//go/platform:plan9": [
            "-Ivendor/github.com/mattn/go-sqlite3",
        ],
        "@io_bazel_rules_go//go/platform:solaris": [
            "-Ivendor/github.com/mattn/go-sqlite3",
        ],
        "@io_bazel_rules_go//go/platform:windows": [
            "-Ivendor/github.com/mattn/go-sqlite3 -fno-stack-check -fno-stack-protector -mno-stack-arg-probe",
        ],
        "//conditions:default": [],
    }) + select({
        "@io_bazel_rules_go//go/platform:windows_386": [
            "-D_USE_32BIT_TIME_T",
        ],
        "//conditions:default": [],
    }),
    importpath = "github.com/mattn/go-sqlite3",
    visibility = ["//visibility:public"],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [":package-srcs"],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
