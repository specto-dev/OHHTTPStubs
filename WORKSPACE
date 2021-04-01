workspace(name = "OHHTTPStubs")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "build_bazel_rules_apple",
    sha256 = "6df1ce430e89231d8690da4e2d9c98d03c8530b0a0ddba742c3f1fc33d4c4ced",
    strip_prefix = "rules_apple-9ee34a4793b5906eba5e5b948c4339c74e29e797",
    url = "https://github.com/specto-dev/rules_apple/archive/9ee34a4793b5906eba5e5b948c4339c74e29e797.tar.gz",
)

load(
    "@build_bazel_rules_apple//apple:repositories.bzl",
    "apple_rules_dependencies",
)

apple_rules_dependencies()

load(
    "@build_bazel_rules_swift//swift:repositories.bzl",
    "swift_rules_dependencies",
)

swift_rules_dependencies()

load(
    "@build_bazel_apple_support//lib:repositories.bzl",
    "apple_support_dependencies",
)

apple_support_dependencies()

# added to fix build errors for //Sources/OHHTTPStubsSwift:swift-lib

http_archive(
    name = "com_google_protobuf",
    sha256 = "18b0a055105afc73d09948beec67b4b56d17ee55b0669cd105d246954adc59ae",
    strip_prefix = "protobuf-3.15.2",
    urls = ["https://github.com/protocolbuffers/protobuf/archive/v3.15.2.zip"],
)

load("@com_google_protobuf//:protobuf_deps.bzl", "protobuf_deps")
protobuf_deps()
