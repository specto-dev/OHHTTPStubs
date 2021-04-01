load(
    "@build_bazel_rules_apple//apple:ios.bzl",
    "ios_static_framework",
)
load(
    "@build_bazel_rules_swift//swift:swift.bzl",
    "swift_library",
)

swift_library(
    name = "lib",
    srcs = glob(["**/*.swift"]),
    module_name = "OHHTTPStubs",
    deps = ["//Sources/OHHTTPStubs:lib"],
)

ios_static_framework(
    name = "ios-framework",
    bundle_name = "OHHTTPStubs",
    families = [
        "iphone",
        "ipad",
    ],
    minimum_os_version = "12.0",
    deps = [
        ":lib",
    ],
)
