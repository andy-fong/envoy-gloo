licenses(["notice"])  # Apache 2

load(
    "@envoy//bazel:envoy_build_system.bzl",
    "envoy_cc_library",
    "envoy_package",
)

envoy_package()

envoy_cc_library(
    name = "client_lib",
    srcs = ["client_impl.cc"],
    hdrs = ["client_impl.h"],
    repository = "@envoy",
    deps = [
        "//include/envoy/nats:codec_interface",
        "//include/envoy/nats/streaming:client_interface",
        "//include/envoy/tcp:conn_pool_interface",
        "//source/common/buffer:buffer_utility_lib",
        "//source/common/nats:message_builder_lib",
        "//source/common/nats:subject_utility_lib",
        "//source/common/nats:token_generator_lib",
        "//source/common/nats/streaming:connect_response_handler_lib",
        "//source/common/nats/streaming:heartbeat_handler_lib",
        "//source/common/nats/streaming:message_utility_lib",
        "//source/common/nats/streaming:pub_request_handler_lib",
    ],
)

envoy_cc_library(
    name = "client_pool_lib",
    srcs = ["client_pool.cc"],
    hdrs = ["client_pool.h"],
    repository = "@envoy",
    deps = [
        "//include/envoy/nats:codec_interface",
        "//include/envoy/nats/streaming:client_interface",
        "//include/envoy/tcp:conn_pool_interface",
        "//source/common/nats:codec_lib",
        "//source/common/nats/streaming:client_lib",
        "//source/common/tcp:conn_pool_lib",
    ],
)

envoy_cc_library(
    name = "connect_response_handler_lib",
    srcs = ["connect_response_handler.cc"],
    hdrs = ["connect_response_handler.h"],
    repository = "@envoy",
    deps = [
        "@envoy//envoy/common:pure_lib",
        "//include/envoy/nats/streaming:inbox_handler_interface",
        "//source/common/nats/streaming:message_utility_lib",
    ],
)

envoy_cc_library(
    name = "heartbeat_handler_lib",
    srcs = ["heartbeat_handler.cc"],
    hdrs = ["heartbeat_handler.h"],
    repository = "@envoy",
    deps = [
        "//include/envoy/nats/streaming:inbox_handler_interface",
        "//source/common/nats:message_builder_lib",
        "@com_google_absl//absl/types:optional",
    ],
)

envoy_cc_library(
    name = "message_utility_lib",
    srcs = ["message_utility.cc"],
    hdrs = ["message_utility.h"],
    repository = "@envoy",
    deps = [
        "//api/envoy/type/streaming:pkg_cc_proto",
        "@com_google_absl//absl/types:optional",
    ],
)

envoy_cc_library(
    name = "pub_request_handler_lib",
    srcs = ["pub_request_handler.cc"],
    hdrs = ["pub_request_handler.h"],
    repository = "@envoy",
    deps = [
        "//include/envoy/nats/streaming:client_interface",
        "//include/envoy/nats/streaming:inbox_handler_interface",
        "//source/common/nats/streaming:message_utility_lib",
        "@envoy//envoy/common:time_interface",
        "@envoy//envoy/event:timer_interface",
        "@envoy//source/common/buffer:buffer_lib",
    ],
)
