package(default_visibility = ["//visibility:public"])
load("@io_bazel_rules_scala//scala:scala.bzl", "scala_binary", "scala_library", "scala_test")

scala_library(
        name = "core",
        srcs = glob([
                "src/main/scala/**/*.scala",
                "src/main/java/**/*.java",
            ],
        ),
        plugins = ["//idslplugin"],
        deps = [
            ":info",
            "//idslplugin",
            "//idslpayload",
            "//sim",
            "@maven//:commons_io_commons_io",
            "@maven//:com_github_scopt_scopt_2_11",
            "@io_bazel_rules_scala_scala_reflect//:io_bazel_rules_scala_scala_reflect"
        ],
)

# TODO
name = "SpinalHDL-core"
version = "1.4.2"

genrule(
        name = "info_src",
        outs = ["src/main/scala/Info.scala"],
        cmd = """cat <<EOF > $@
package spinal.core
object Info {
  val version = "%s"
  val name = "%s"
  val gitHash = "%s"
}
EOF""" % (version, name, "DIRTY"),
)


scala_library(
        name = "info",
        srcs = [":info_src"],
)

# TODO
scala_test(
        name = "core_test",
        srcs = glob([
                "src/test/scala/**/*.scala",
            ],
        ),
        plugins = ["//idslplugin"],
        deps = [
            ":core",
            "//idslplugin",
            "//idslpayload",
            "//sim",
            #"@maven//:commons_io_commons_io",
            #"@maven//:com_github_scopt_scopt_2_11",
            #"@io_bazel_rules_scala_scala_reflect//:io_bazel_rules_scala_scala_reflect"
        ],
)
