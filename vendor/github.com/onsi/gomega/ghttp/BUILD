load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "handlers.go",
        "test_server.go",
    ],
    importpath = "github.com/onsi/gomega/ghttp",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/golang/protobuf/proto:go_default_library",
        "//vendor/github.com/onsi/gomega:go_default_library",
        "//vendor/github.com/onsi/gomega/types:go_default_library",
    ],
)

go_test(
    name = "go_default_xtest",
    srcs = [
        "test_server_suite_test.go",
        "test_server_test.go",
    ],
    importpath = "github.com/onsi/gomega/ghttp_test",
    deps = [
        ":go_default_library",
        "//vendor/github.com/golang/protobuf/proto:go_default_library",
        "//vendor/github.com/onsi/ginkgo:go_default_library",
        "//vendor/github.com/onsi/gomega:go_default_library",
        "//vendor/github.com/onsi/gomega/gbytes:go_default_library",
        "//vendor/github.com/onsi/gomega/ghttp/protobuf:go_default_library",
    ],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [
        ":package-srcs",
        "//vendor/github.com/onsi/gomega/ghttp/protobuf:all-srcs",
    ],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
