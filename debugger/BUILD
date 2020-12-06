package(default_visibility = ["//visibility:public"])
load("@io_bazel_rules_scala//scala:scala.bzl", "scala_binary", "scala_library")

scala_library(
        name = "debugger",
        srcs = glob([
                "src/main/scala/**/*.scala",
                #"src/main/java/**/*.java",
             ],
        ),
        plugins = ["//idslplugin"],
        deps = [
            "//core",
            "//lib",
            "@maven//:net_liftweb_lift_json_2_11",
            "@maven//:com_github_purejavacomm_purejavacomm",
            #"//sim",
            #"@maven//:commons_io_commons_io",
            #"@maven//:com_github_oshi_oshi_core",
            "//idslplugin",
            "//idslpayload",
        ],
)


