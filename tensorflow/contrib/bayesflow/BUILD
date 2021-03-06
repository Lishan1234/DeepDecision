# Description:
#   Contains ops for working with statistical distributions,
#   particularly useful for Bayesian inference.
#   APIs here are meant to evolve over time.

licenses(["notice"])  # Apache 2.0

exports_files(["LICENSE"])

package(default_visibility = ["//tensorflow:__subpackages__"])

load("//tensorflow:tensorflow.bzl", "cuda_py_test")

py_library(
    name = "bayesflow_py",
    srcs = ["__init__.py"] + glob(["python/ops/*.py"]),
    srcs_version = "PY2AND3",
    deps = [
        "//tensorflow/python:array_ops",
        "//tensorflow/python:check_ops",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:nn",
        "//tensorflow/python:platform",
        "//tensorflow/python:training",
        "//tensorflow/python:util",
        "//tensorflow/python:variable_scope",
        "//tensorflow/python/ops/distributions",
        "//third_party/py/numpy",
        "@six_archive//:six",
    ],
)

cuda_py_test(
    name = "csiszar_divergence_test",
    size = "small",
    srcs = ["python/kernel_tests/csiszar_divergence_test.py"],
    additional_deps = [
        ":bayesflow_py",
        "//third_party/py/numpy",
        "//tensorflow/contrib/distributions:distributions_py",
        "//tensorflow/contrib/layers:layers_py",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:nn_ops",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "entropy_test",
    size = "medium",
    srcs = ["python/kernel_tests/entropy_test.py"],
    additional_deps = [
        ":bayesflow_py",
        "//third_party/py/numpy",
        "//tensorflow/contrib/distributions:distributions_py",
        "//tensorflow/contrib/layers:layers_py",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:nn_ops",
        "//tensorflow/python:platform_test",
        "//tensorflow/python:variables",
    ],
)

cuda_py_test(
    name = "stochastic_variables_test",
    size = "medium",
    srcs = ["python/kernel_tests/stochastic_variables_test.py"],
    additional_deps = [
        ":bayesflow_py",
        "//third_party/py/numpy",
        "//tensorflow/contrib/distributions:distributions_py",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:platform_test",
        "//tensorflow/python:random_ops",
        "//tensorflow/python:variable_scope",
        "//tensorflow/python:variables",
    ],
)

cuda_py_test(
    name = "monte_carlo_test",
    size = "small",
    srcs = ["python/kernel_tests/monte_carlo_test.py"],
    additional_deps = [
        ":bayesflow_py",
        "//third_party/py/numpy",
        "//tensorflow/contrib/distributions:distributions_py",
        "//tensorflow/contrib/layers:layers_py",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "stochastic_graph_test",
    size = "small",
    srcs = ["python/kernel_tests/stochastic_graph_test.py"],
    additional_deps = [
        ":bayesflow_py",
        "//tensorflow/contrib/distributions:distributions_py",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:control_flow_ops",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:gradients",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "variational_inference_test",
    size = "small",
    srcs = ["python/kernel_tests/variational_inference_test.py"],
    additional_deps = [
        ":bayesflow_py",
        "//tensorflow/contrib/distributions:distributions_py",
        "//tensorflow/contrib/layers:layers_py",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:platform_test",
        "//tensorflow/python:variables",
    ],
)

cuda_py_test(
    name = "stochastic_tensor_test",
    size = "small",
    srcs = ["python/kernel_tests/stochastic_tensor_test.py"],
    additional_deps = [
        ":bayesflow_py",
        "//third_party/py/numpy",
        "//tensorflow/contrib/distributions:distributions_py",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "stochastic_gradient_estimators_test",
    size = "medium",
    srcs = ["python/kernel_tests/stochastic_gradient_estimators_test.py"],
    additional_deps = [
        ":bayesflow_py",
        "//third_party/py/numpy",
        "//tensorflow/contrib/distributions:distributions_py",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:gradients",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:platform_test",
        "//tensorflow/python:variables",
    ],
)

cuda_py_test(
    name = "reinforce_simple_example",
    size = "small",
    srcs = ["examples/reinforce_simple/reinforce_simple_example.py"],
    additional_deps = [
        ":bayesflow_py",
        "//tensorflow:tensorflow_py",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:platform_test",
    ],
)

filegroup(
    name = "all_files",
    srcs = glob(
        ["**/*"],
        exclude = [
            "**/METADATA",
            "**/OWNERS",
        ],
    ),
    visibility = ["//tensorflow:__subpackages__"],
)
