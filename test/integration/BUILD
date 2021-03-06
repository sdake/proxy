# Copyright 2018 Istio Authors. All Rights Reserved.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#    http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#
################################################################################

package(default_visibility = ["//visibility:public"])

load(
    "@envoy//bazel:envoy_build_system.bzl",
    "envoy_cc_test",
    "envoy_cc_test_library",
)

envoy_cc_test_library(
    name = "int_client_server",
    srcs = [
        "int_client.cc",
        "int_server.cc",
    ],
    hdrs = [
        "int_client.h",
        "int_server.h",
    ],
    repository = "@envoy",
    deps = [
        "@envoy//source/server:server_lib",
        "@envoy//test/integration:http_protocol_integration_lib",
    ],
)

envoy_cc_test(
    name = "istio_http_integration_test",
    srcs = [
        "istio_http_integration_test.cc",
    ],
    repository = "@envoy",
    deps = [
        "//include/istio/utils:attribute_names_header",
        "//src/envoy/http/authn:filter_lib",
        "//src/envoy/http/jwt_auth:http_filter_factory",
        "//src/envoy/http/jwt_auth:jwt_lib",
        "//src/envoy/http/mixer:filter_lib",
        "//src/envoy/utils:filter_names_lib",
        "@envoy//source/common/common:utility_lib",
        "@envoy//test/integration:http_protocol_integration_lib",
    ],
)

envoy_cc_test(
    name = "istio_http_integration_test_with_envoy_jwt_filter",
    srcs = [
        "istio_http_integration_test_with_envoy_jwt_filter.cc",
    ],
    repository = "@envoy",
    deps = [
        "//include/istio/utils:attribute_names_header",
        "//src/envoy/http/authn:filter_lib",
        "//src/envoy/http/jwt_auth:http_filter_factory",
        "//src/envoy/http/jwt_auth:jwt_lib",
        "//src/envoy/http/mixer:filter_lib",
        "//src/envoy/utils:filter_names_lib",
        "@envoy//source/common/common:utility_lib",
        "@envoy//test/integration:http_protocol_integration_lib",
    ],
)

envoy_cc_test(
    name = "mixer_fault_test",
    srcs = [
        "mixer_fault_test.cc",
    ],
    repository = "@envoy",
    deps = [
        ":int_client_server",
        "//include/istio/utils:attribute_names_header",
        "//src/envoy/http/mixer:filter_lib",
        "//src/envoy/utils:filter_names_lib",
    ],
)

envoy_cc_test(
    name = "int_client_server_test",
    srcs = [
        "int_client_server_test.cc",
    ],
    repository = "@envoy",
    deps = [
        ":int_client_server",
    ],
)

envoy_cc_test(
    name = "exchanged_token_integration_test",
    srcs = ["exchanged_token_integration_test.cc"],
    repository = "@envoy",
    deps = [
        "//include/istio/utils:attribute_names_header",
        "//src/envoy/http/authn:filter_lib",
        "//src/envoy/http/jwt_auth:http_filter_factory",
        "//src/envoy/http/jwt_auth:jwt_lib",
        "//src/envoy/http/mixer:filter_lib",
        "//src/envoy/utils:filter_names_lib",
        "@envoy//source/common/common:utility_lib",
        "@envoy//test/integration:http_protocol_integration_lib",
    ],
)
