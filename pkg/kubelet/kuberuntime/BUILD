package(default_visibility = ["//visibility:public"])

load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_library",
    "go_test",
)

go_library(
    name = "go_default_library",
    srcs = [
        "doc.go",
        "fake_kuberuntime_manager.go",
        "helpers.go",
        "helpers_linux.go",
        "helpers_unsupported.go",
        "instrumented_services.go",
        "kuberuntime_container.go",
        "kuberuntime_container_linux.go",
        "kuberuntime_container_unsupported.go",
        "kuberuntime_container_windows.go",
        "kuberuntime_gc.go",
        "kuberuntime_image.go",
        "kuberuntime_logs.go",
        "kuberuntime_manager.go",
        "kuberuntime_sandbox.go",
        "labels.go",
        "legacy.go",
        "security_context.go",
    ],
    importpath = "k8s.io/kubernetes/pkg/kubelet/kuberuntime",
    deps = [
        "//pkg/api/legacyscheme:go_default_library",
        "//pkg/credentialprovider:go_default_library",
        "//pkg/credentialprovider/secrets:go_default_library",
        "//pkg/features:go_default_library",
        "//pkg/kubelet/cm:go_default_library",
        "//pkg/kubelet/container:go_default_library",
        "//pkg/kubelet/events:go_default_library",
        "//pkg/kubelet/images:go_default_library",
        "//pkg/kubelet/kuberuntime/logs:go_default_library",
        "//pkg/kubelet/lifecycle:go_default_library",
        "//pkg/kubelet/metrics:go_default_library",
        "//pkg/kubelet/prober/results:go_default_library",
        "//pkg/kubelet/runtimeclass:go_default_library",
        "//pkg/kubelet/types:go_default_library",
        "//pkg/kubelet/util/cache:go_default_library",
        "//pkg/kubelet/util/format:go_default_library",
        "//pkg/kubelet/util/logreduction:go_default_library",
        "//pkg/security/apparmor:go_default_library",
        "//pkg/securitycontext:go_default_library",
        "//pkg/util/parsers:go_default_library",
        "//pkg/util/selinux:go_default_library",
        "//pkg/util/tail:go_default_library",
        "//pkg/volume/util:go_default_library",
        "//staging/src/k8s.io/api/core/v1:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/apis/meta/v1:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/types:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/util/errors:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/util/runtime:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/util/sets:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/util/version:go_default_library",
        "//staging/src/k8s.io/apiserver/pkg/util/feature:go_default_library",
        "//staging/src/k8s.io/client-go/tools/record:go_default_library",
        "//staging/src/k8s.io/client-go/tools/reference:go_default_library",
        "//staging/src/k8s.io/client-go/util/flowcontrol:go_default_library",
        "//staging/src/k8s.io/cri-api/pkg/apis:go_default_library",
        "//staging/src/k8s.io/cri-api/pkg/apis/runtime/v1alpha2:go_default_library",
        "//vendor/github.com/armon/circbuf:go_default_library",
        "//vendor/github.com/google/cadvisor/info/v1:go_default_library",
        "//vendor/google.golang.org/grpc/status:go_default_library",
        "//vendor/k8s.io/klog/v2:go_default_library",
    ] + select({
        "@io_bazel_rules_go//go/platform:android": [
            "//pkg/apis/core/v1/helper:go_default_library",
            "//pkg/kubelet/qos:go_default_library",
            "//vendor/github.com/opencontainers/runc/libcontainer/cgroups/fs:go_default_library",
        ],
        "@io_bazel_rules_go//go/platform:linux": [
            "//pkg/apis/core/v1/helper:go_default_library",
            "//pkg/kubelet/qos:go_default_library",
            "//vendor/github.com/opencontainers/runc/libcontainer/cgroups/fs:go_default_library",
        ],
        "@io_bazel_rules_go//go/platform:windows": [
            "//pkg/kubelet/apis:go_default_library",
        ],
        "//conditions:default": [],
    }),
)

go_test(
    name = "go_default_test",
    srcs = [
        "helpers_linux_test.go",
        "helpers_test.go",
        "instrumented_services_test.go",
        "kuberuntime_container_linux_test.go",
        "kuberuntime_container_test.go",
        "kuberuntime_gc_test.go",
        "kuberuntime_image_test.go",
        "kuberuntime_manager_test.go",
        "kuberuntime_sandbox_test.go",
        "labels_test.go",
        "legacy_test.go",
        "security_context_test.go",
    ],
    embed = [":go_default_library"],
    deps = [
        "//pkg/api/v1/pod:go_default_library",
        "//pkg/credentialprovider:go_default_library",
        "//pkg/features:go_default_library",
        "//pkg/kubelet/container:go_default_library",
        "//pkg/kubelet/container/testing:go_default_library",
        "//pkg/kubelet/lifecycle:go_default_library",
        "//pkg/kubelet/metrics:go_default_library",
        "//pkg/kubelet/prober/results:go_default_library",
        "//pkg/kubelet/runtimeclass:go_default_library",
        "//pkg/kubelet/runtimeclass/testing:go_default_library",
        "//staging/src/k8s.io/api/core/v1:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/apis/meta/v1:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/types:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/util/intstr:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/util/sets:go_default_library",
        "//staging/src/k8s.io/apiserver/pkg/util/feature:go_default_library",
        "//staging/src/k8s.io/client-go/util/flowcontrol:go_default_library",
        "//staging/src/k8s.io/component-base/featuregate/testing:go_default_library",
        "//staging/src/k8s.io/component-base/metrics/legacyregistry:go_default_library",
        "//staging/src/k8s.io/cri-api/pkg/apis/runtime/v1alpha2:go_default_library",
        "//staging/src/k8s.io/cri-api/pkg/apis/testing:go_default_library",
        "//vendor/github.com/golang/mock/gomock:go_default_library",
        "//vendor/github.com/google/cadvisor/info/v1:go_default_library",
        "//vendor/github.com/google/go-cmp/cmp:go_default_library",
        "//vendor/github.com/stretchr/testify/assert:go_default_library",
        "//vendor/github.com/stretchr/testify/require:go_default_library",
        "//vendor/k8s.io/utils/pointer:go_default_library",
    ] + select({
        "@io_bazel_rules_go//go/platform:android": [
            "//staging/src/k8s.io/apimachinery/pkg/api/resource:go_default_library",
            "//vendor/github.com/opencontainers/runc/libcontainer/cgroups/fs:go_default_library",
        ],
        "@io_bazel_rules_go//go/platform:linux": [
            "//staging/src/k8s.io/apimachinery/pkg/api/resource:go_default_library",
            "//vendor/github.com/opencontainers/runc/libcontainer/cgroups/fs:go_default_library",
        ],
        "//conditions:default": [],
    }),
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [
        ":package-srcs",
        "//pkg/kubelet/kuberuntime/logs:all-srcs",
    ],
    tags = ["automanaged"],
)
