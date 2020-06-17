package(default_visibility = ["//visibility:public"])

load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_library")
load("@bazel_tools//tools/build_defs/pkg:pkg.bzl", "pkg_tar")
load("//:build/workspace.bzl", "RELEASE_VERSION")

#build package of dashboard.
pkg_tar(
    name = "applet-" + RELEASE_VERSION,
    extension = "tar.gz",
    srcs = [":applet"],
    mode = "0755",
)

go_binary(
    name = "applet",
    embed = [":main"],
)

go_library(
    name = "main",
    srcs = ["app.go"],
    importpath = "applet",
)