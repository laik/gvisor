load("@io_bazel_rules_go//go:def.bzl", "go_test")
load("//tools/go_stateify:defs.bzl", "go_library")

package(licenses = ["notice"])

go_library(
    name = "ramfs",
    srcs = [
        "dir.go",
        "socket.go",
        "symlink.go",
        "tree.go",
    ],
    importpath = "gvisor.dev/gvisor/pkg/sentry/fs/ramfs",
    visibility = ["//pkg/sentry:internal"],
    deps = [
        "//pkg/abi/linux",
        "//pkg/sentry/context",
        "//pkg/sentry/fs",
        "//pkg/sentry/fs/anon",
        "//pkg/sentry/fs/fsutil",
        "//pkg/sentry/socket/unix/transport",
        "//pkg/sentry/usermem",
        "//pkg/syserror",
        "//pkg/waiter",
    ],
)

go_test(
    name = "ramfs_test",
    size = "small",
    srcs = ["tree_test.go"],
    embed = [":ramfs"],
    deps = [
        "//pkg/sentry/context/contexttest",
        "//pkg/sentry/fs",
    ],
)
