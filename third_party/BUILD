
package(
    default_visibility = ["//visibility:public"],
)

licenses(["notice"])

cc_library(
    name = "libtensorflow",
    hdrs = glob(["include/**/*.h"]),
    includes = ["include"],
    deps = select({
        "@bazel_tools//src/conditions:windows" : ["libtensorflow_win"],
        "//conditions:default" : [":libtensorflow_", ":libtensorflow_framework"],
    }),
)

cc_import(
    name = "libtensorflow_win",
    shared_library = "lib/tensorflow.dll",
    interface_library = "lib/tensorflow.lib",
)

cc_import(
    name = "libtensorflow_",
    shared_library = "lib/libtensorflow.so",
)

cc_import(
    name = "libtensorflow_framework",
    shared_library = "lib/libtensorflow_framework.so",
)
