load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")
load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive", "http_file")

git_repository(
	name = "io_bazel_rules_go",
	remote = "https://github.com/bazelbuild/rules_go.git",
	tag = "0.19.1",
)

load("@io_bazel_rules_go//go:deps.bzl", "go_download_sdk", "go_rules_dependencies", "go_register_toolchains")
go_rules_dependencies()

go_download_sdk(
	name = "go_sdk",
	sdks = {
		"linux_amd64": ("go1.11.5.linux-amd64.tar.gz", "ff54aafedff961eb94792487e827515da683d61a5f9482f668008832631e5d25"),
	},
)

http_archive(
	name = "bazel_gazelle",
	urls = ["https://github.com/bazelbuild/bazel-gazelle/releases/download/0.18.1/bazel-gazelle-0.18.1.tar.gz"],
	sha256 = "be9296bfd64882e3c08e3283c58fcb461fa6dd3c171764fcc4cf322f60615a9b",
)

load("@bazel_gazelle//:deps.bzl", "gazelle_dependencies", "go_repository")
gazelle_dependencies()
