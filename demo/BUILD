package(default_visibility = ["//visibility:public"])
load("@io_bazel_rules_scala//scala:scala.bzl", "scala_binary", "scala_library")

scala_library(
        name = "demo",
        srcs = glob(["src/main/scala/**/*.scala"]),
        plugins = ["//idslplugin"],
        deps = [
            "//core",
            "//lib",
            "//debugger",
            "//idslplugin",
            "//idslpayload",
            "@maven//:net_liftweb_lift_json_2_11",
        ],
)

scala_binary(
        name = "demo_bin",
        main_class="spinal.demo.mandelbrot.MandelbrotSblDemo",
        plugins = ["//idslplugin"],
        deps = [
            ":demo",
            "//core",
            "//lib",
            "//debugger",
            "//idslplugin",
            "//idslpayload",
            "@maven//:net_liftweb_lift_json_2_12",
        ],
)
