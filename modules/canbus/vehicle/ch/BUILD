load("//tools:cpplint.bzl", "cpplint")

package(default_visibility = ["//visibility:public"])

cc_library(
    name = "ch_vehicle_factory",
    srcs = [
        "ch_vehicle_factory.cc",
    ],
    hdrs = [
        "ch_vehicle_factory.h",
    ],
    deps = [
        ":ch_controller",
        ":ch_message_manager",
        "//modules/canbus/vehicle:abstract_vehicle_factory",
    ],
)

cc_library(
    name = "ch_message_manager",
    srcs = [
        "ch_message_manager.cc",
    ],
    hdrs = [
        "ch_message_manager.h",
    ],
    deps = [
        "//modules/drivers/canbus/common:canbus_common",
        "//modules/canbus/proto:canbus_proto",
        "//modules/drivers/canbus/can_comm:message_manager_base",
        "//modules/canbus/vehicle/ch/protocol:canbus_ch_protocol",
    ],
)

cc_library(
    name = "ch_controller",
    srcs = [
        "ch_controller.cc",
    ],
    hdrs = [
        "ch_controller.h",
    ],
    deps = [
        ":ch_message_manager",
        "//modules/drivers/canbus/can_comm:can_sender",
        "//modules/drivers/canbus/common:canbus_common",
        "//modules/canbus/proto:canbus_proto",
        "//modules/drivers/canbus/can_comm:message_manager_base",
        "//modules/canbus/vehicle:vehicle_controller_base",
        "//modules/canbus/vehicle/ch/protocol:canbus_ch_protocol",
    ],
)

cc_test(
    name = "ch_controller_test",
    size = "small",
    srcs = [
        "ch_controller_test.cc",
    ],
    data = ["//modules/canbus:canbus_testdata"],
    deps = [
        ":ch_controller",
        "@gtest//:main",
    ],
)

cc_test(
    name = "ch_message_manager_test",
    size = "small",
    srcs = [
        "ch_message_manager_test.cc",
    ],
    deps = [
        "//modules/canbus/vehicle/ch:ch_message_manager",
        "@gtest//:main",
    ],
)

cc_test(
    name = "ch_vehicle_factory_test",
    size = "small",
    srcs = ["ch_vehicle_factory_test.cc"],
    deps = [
        ":ch_vehicle_factory",
        "@gtest//:main",
    ],
)

cpplint()
