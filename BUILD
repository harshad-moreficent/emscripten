load("@com_github_bazelbuild_buildtools//buildifier:def.bzl", "buildifier")
load("@rules_python//python:defs.bzl", "py_runtime", "py_runtime_pair")

buildifier(
    name = "buildifier",
)

py_runtime(
    name = "python3_runtime",
    files = ["@python_interpreter//:files"],
    interpreter = "@python_interpreter//:python_bin",
    python_version = "PY3",
    visibility = ["//visibility:public"],
)

py_runtime_pair(
    name = "emscripten_py_runtime_pair",
    py2_runtime = None,
    py3_runtime = ":python3_runtime",
)

toolchain(
    name = "emscripten_py_toolchain",
    toolchain = ":emscripten_py_runtime_pair",
    toolchain_type = "@bazel_tools//tools/python:toolchain_type",
)
