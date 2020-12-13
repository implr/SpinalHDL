package(default_visibility = ["//visibility:public"])
load("@io_bazel_rules_scala//scala:scala.bzl", "scala_binary", "scala_macro_library", "scala_library")

# TODO granular
scala_macro_library(
        name = "lib",
        srcs = glob([
                "src/main/scala/**/*.scala",
                #"src/main/java/**/*.java",
             ],
        ),
        plugins = ["//idslplugin"],
        deps = [
            "//core",
            "//sim",
            "@maven//:commons_io_commons_io",
            #"@io_bazel_rules_scala_scala_compiler//:io_bazel_rules_scala_scala_compiler",
            #"@io_bazel_rules_scala_scala_library//:io_bazel_rules_scala_scala_library"
            "@maven//:com_github_oshi_oshi_core",
            #"@maven//:net_openhft_affinity",
            #"@maven//:org_slf4j_slf4j_simple",
            "//idslplugin",
            "//idslpayload",
        ],
)


