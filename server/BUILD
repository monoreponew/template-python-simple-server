load("@rules_python//python:defs.bzl", "py_binary")
load("@genrules//google_cloud_run:index.bzl", "deploy")

py_binary(
    name = "server",
    srcs = ["server.py"],
    visibility = ["//visibility:public"],
)

deploy(
    name = "python_service",
    binary = ":server",
    port = "8000",
    base_image="python",
)
