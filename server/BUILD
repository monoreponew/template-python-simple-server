load("@rules_python//python:defs.bzl", "py_binary")
load("@io_bazel_rules_docker//python3:image.bzl", "py3_image")
load("@genrules//google_cloud_run:index.bzl", "deploy")

py_binary(
    name = "server",
    srcs = ["server.py"],
    visibility = ["//visibility:public"],
)

py3_image(
    name = "server_image",
    main = "server.py",
    srcs = ["server.py"],
    visibility = ["//visibility:public"],
)

deploy(
    name = "python_service",
    target = ":server_image",
    port = "8000",
)
