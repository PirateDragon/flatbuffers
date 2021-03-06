package(
    default_visibility = ["//visibility:private"],
)

load("@rules_cc//cc:defs.bzl", "cc_binary", "cc_library")

# Public flatc library to compile flatbuffer files at runtime.
cc_library(
    name = "flatbuffers",
    srcs = [
        "code_generators.cpp",
        "idl_gen_fbs.cpp",
        "idl_gen_text.cpp",
        "idl_parser.cpp",
        "reflection.cpp",
        "util.cpp",
    ],
    hdrs = ["//:public_headers"],
    strip_include_prefix = "/include",
    visibility = ["//:__pkg__"],
)

# Public flatc compiler library.
cc_library(
    name = "flatc_library",
    srcs = [
        "flatc.cpp",
    ],
    hdrs = [
        "//:flatc_headers",
    ],
    strip_include_prefix = "/include",
    visibility = ["//:__pkg__"],
    deps = [
        ":flatbuffers",
    ],
)

# Public flatc compiler.
cc_library(
    name = "flatc",
    srcs = [
        "flatc_main.cpp",
        "idl_gen_cpp.cpp",
        "idl_gen_csharp.cpp",
        "idl_gen_dart.cpp",
        "idl_gen_go.cpp",
        "idl_gen_grpc.cpp",
        "idl_gen_java.cpp",
        "idl_gen_js_ts.cpp",
        "idl_gen_json_schema.cpp",
        "idl_gen_kotlin.cpp",
        "idl_gen_lobster.cpp",
        "idl_gen_lua.cpp",
        "idl_gen_php.cpp",
        "idl_gen_python.cpp",
        "idl_gen_rust.cpp",
        "idl_gen_swift.cpp",
        "idl_gen_text.cpp",
        "util.cpp",
    ],
    hdrs = [
        "//:flatc_headers",
    ],
    strip_include_prefix = "/include",
    visibility = ["//:__pkg__"],
    deps = [
        ":flatc_library",
        "//grpc/src/compiler:cpp_generator",
        "//grpc/src/compiler:go_generator",
        "//grpc/src/compiler:java_generator",
        "//grpc/src/compiler:python_generator",
        "//grpc/src/compiler:swift_generator",
    ],
)
