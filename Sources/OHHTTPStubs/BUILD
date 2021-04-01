load(
    "@build_bazel_rules_apple//apple:ios.bzl",
    "ios_static_framework",
)

_PUBLIC_HEADERS = [
    "include/Compatibility.h",
    "include/HTTPStubs.h",
    "include/HTTPStubsPathHelpers.h",
    "include/HTTPStubsResponse.h",
    "include/HTTPStubsResponse+JSON.h",
    "include/NSURLRequest+HTTPBodyTesting.h",
]

objc_library(
    name = "lib",
    srcs = glob(
        [
            "**/*.h",
            "**/*.m",
        ],
        exclude = _PUBLIC_HEADERS,
    ),
    hdrs = _PUBLIC_HEADERS,
    includes = ["include"],
    visibility = ["//visibility:public"],
)

ios_static_framework(
    name = "ios-framework",
    hdrs = _PUBLIC_HEADERS,
    bundle_name = "OHHTTPStubs",
    families = [
        "iphone",
        "ipad",
    ],
    minimum_os_version = "12.0",
    umbrella_header = "//Sources/Supporting Files:OHHTTPStubs.h",
    deps = [
        ":lib",
    ],
)
