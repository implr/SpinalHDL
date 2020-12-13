package(default_visibility = ["//visibility:public"])
load("@io_bazel_rules_scala//scala:scala.bzl", "scala_binary", "scala_library", "scala_test", "scala_test_suite")

scala_library(
        name = "tester",
        srcs = glob(["src/main/scala/**/*.scala"]),
                     #"src/main/java/**/*.java"]),
        plugins = ["//idslplugin"],
        deps = [
            ":tester_java",
            "//core",
            "//lib",
            "//debugger",
            "//demo",
            "//sim",
            "//idslplugin",
            "//idslpayload",
            "@maven//:net_liftweb_lift_json_2_11",
            "@maven//:com_github_scopt_scopt_2_11",
            "@maven//:net_openhft_affinity",
        ],
)

java_library(
        name = "tester_java",
        srcs = glob(["src/main/java/**/*.java"]),
)

scala_library(
        name = "suite_deps",
        srcs = ["src/test/scala/spinal/tester/scalatest/" + i for i in
                ["SpinalTesterCocotbBase.scala",
                 "SpinalTesterGhdlBase.scala",
                 "SpinalSimMiscTester.scala",
                 "SpinalSimVerilatorIoTest.scala",
                 "StreamTester.scala",
                 "SpinalSimBmbInterconnectGeneratorTester.scala",
                 "FixedPointTester.scala",
                 "ChecksTester.scala",
                 "GrayCounterTester.scala",
                 ]],
        deps = [
            ":tester",
            ":tester_java",
            "//core",
            "//sim",
            "//lib",
            "//demo",
            "//idslplugin",
            "//idslpayload",
            "@maven//:commons_io_commons_io",
            "@io_bazel_rules_scala_scalatest//:io_bazel_rules_scala_scalatest",
            "@io_bazel_rules_scala_scalactic//:io_bazel_rules_scala_scalactic",
        ],
)
scala_binary(
        name = "foo",
        main_class = "spinal.tester.scalatest.Run",
        srcs = ["src/test/scala/spinal/tester/scalatest/SpinalSimMiscTester.scala"],
        deps = [
            ":suite_deps",
            ":tester",
            ":tester_java",
            "//core",
            "//sim",
            "//lib",
            "//demo",
            "//idslplugin",
            "//idslpayload",
            "@maven//:commons_io_commons_io",
            "@maven//:net_liftweb_lift_json_2_11",
            "@io_bazel_rules_scala_scalatest//:io_bazel_rules_scala_scalatest",
            "@io_bazel_rules_scala_scalactic//:io_bazel_rules_scala_scalactic",
        ],
)

scala_test_suite(
        name = "tester_test",
        srcs = glob([
                "src/test/scala/**/*.scala",
            ],
        ),
        plugins = ["//idslplugin"],
        deps = [
            ":suite_deps",
            ":tester",
            ":tester_java",
            "//core",
            "//sim",
            "//lib",
            "//demo",
            "//idslplugin",
            "//idslpayload",
            "@maven//:commons_io_commons_io",
            "@maven//:net_liftweb_lift_json_2_11",
            #"@maven//:com_github_scopt_scopt_2_11",
            #"@io_bazel_rules_scala_scala_reflect//:io_bazel_rules_scala_scala_reflect"
        ],
)
