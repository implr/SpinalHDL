package(default_visibility = ["//visibility:public"])
load("@io_bazel_rules_scala//scala:scala.bzl", "scala_binary", "scala_library")

scala_library(
        name = "sim",
        srcs = glob([
                "src/main/scala/**/*.scala",
                "src/main/java/**/*.java",
             ],
        ),
        deps = [
            "@maven//:commons_io_commons_io",
            "@maven//:com_github_oshi_oshi_core",
            "@maven//:net_openhft_affinity",
            "@maven//:org_slf4j_slf4j_simple",
        ],
)

