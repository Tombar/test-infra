package(default_visibility = ["//visibility:public"])

load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_library",
    "go_test",
)

go_library(
    name = "go_default_library",
    srcs = [
        "author_filter_wrapper.go",
        "author_logger_wrapper.go",
        "bundle.go",
        "comment_counter.go",
        "count.go",
        "dummy.go",
        "event_counter.go",
        "events.go",
        "fake_comment_wrapper.go",
        "fake_open_wrapper.go",
        "multiplexer_wrapper.go",
        "plugin.go",
        "state.go",
        "states.go",
        "type_filter_wrapper.go",
    ],
    importpath = "k8s.io/test-infra/velodrome/transform/plugins",
    deps = [
        "//velodrome/sql:go_default_library",
        "//vendor/github.com/spf13/cobra:go_default_library",
    ],
)

filegroup(
    name = "configs",
    srcs = glob(["*.yaml"]),
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
)

go_test(
    name = "go_default_test",
    srcs = [
        "author_filter_wrapper_test.go",
        "author_logger_wrapper_test.go",
        "bundle_test.go",
        "comment_counter_test.go",
        "event_counter_test.go",
        "events_test.go",
        "fake_comment_wrapper_test.go",
        "fake_open_wrapper_test.go",
        "multiplexer_wrapper_test.go",
        "plugin_mock_test.go",
        "state_test.go",
        "states_test.go",
        "type_filter_wrapper_test.go",
    ],
    embed = [":go_default_library"],
    importpath = "k8s.io/test-infra/velodrome/transform/plugins",
    deps = [
        "//velodrome/sql:go_default_library",
        "//vendor/github.com/golang/mock/gomock:go_default_library",
    ],
)
