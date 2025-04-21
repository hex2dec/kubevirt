workspace(name = "kubevirt")

load("//third_party:deps.bzl", "deps")

deps()

# register crosscompiler toolchains
load("//bazel/toolchain:toolchain.bzl", "register_all_toolchains")

register_all_toolchains()

load(
    "@bazel_tools//tools/build_defs/repo:http.bzl",
    "http_archive",
    "http_file",
)
load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

http_archive(
    name = "rules_python",
    sha256 = "934c9ceb552e84577b0faf1e5a2f0450314985b4d8712b2b70717dc679fdc01b",
    urls = [
        "https://github.com/bazelbuild/rules_python/releases/download/0.3.0/rules_python-0.3.0.tar.gz",
        "https://storage.googleapis.com/builddeps/934c9ceb552e84577b0faf1e5a2f0450314985b4d8712b2b70717dc679fdc01b",
    ],
)

# Additional bazel rules
http_archive(
    name = "rules_proto",
    sha256 = "bc12122a5ae4b517fa423ea03a8d82ea6352d5127ea48cb54bc324e8ab78493c",
    strip_prefix = "rules_proto-af6481970a34554c6942d993e194a9aed7987780",
    urls = [
        "https://github.com/bazelbuild/rules_proto/archive/af6481970a34554c6942d993e194a9aed7987780.tar.gz",
        "https://storage.googleapis.com/builddeps/bc12122a5ae4b517fa423ea03a8d82ea6352d5127ea48cb54bc324e8ab78493c",
    ],
)

load("@rules_proto//proto:repositories.bzl", "rules_proto_dependencies", "rules_proto_toolchains")

rules_proto_dependencies()

rules_proto_toolchains()

http_archive(
    name = "io_bazel_rules_go",
    sha256 = "91585017debb61982f7054c9688857a2ad1fd823fc3f9cb05048b0025c47d023",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_go/releases/download/v0.42.0/rules_go-v0.42.0.zip",
        "https://github.com/bazelbuild/rules_go/releases/download/v0.42.0/rules_go-v0.42.0.zip",
        "https://storage.googleapis.com/builddeps/91585017debb61982f7054c9688857a2ad1fd823fc3f9cb05048b0025c47d023",
    ],
)

# FIXME: added to make update of gazelle possible, see https://github.com/bazelbuild/bazel-gazelle/issues/1290#issuecomment-1312809060
http_archive(
    name = "bazel_skylib",
    sha256 = "c6966ec828da198c5d9adbaa94c05e3a1c7f21bd012a0b29ba8ddbccb2c93b0d",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/bazel-skylib/releases/download/1.1.1/bazel-skylib-1.1.1.tar.gz",
        "https://github.com/bazelbuild/bazel-skylib/releases/download/1.1.1/bazel-skylib-1.1.1.tar.gz",
        "https://storage.googleapis.com/builddeps/c6966ec828da198c5d9adbaa94c05e3a1c7f21bd012a0b29ba8ddbccb2c93b0d",
    ],
)

http_archive(
    name = "bazel_gazelle",
    sha256 = "d3fa66a39028e97d76f9e2db8f1b0c11c099e8e01bf363a923074784e451f809",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/bazel-gazelle/releases/download/v0.33.0/bazel-gazelle-v0.33.0.tar.gz",
        "https://github.com/bazelbuild/bazel-gazelle/releases/download/v0.33.0/bazel-gazelle-v0.33.0.tar.gz",
        "https://storage.googleapis.com/builddeps/d3fa66a39028e97d76f9e2db8f1b0c11c099e8e01bf363a923074784e451f809",
    ],
)

http_archive(
    name = "io_bazel_rules_docker",
    sha256 = "95d39fd84ff4474babaf190450ee034d958202043e366b9fc38f438c9e6c3334",
    strip_prefix = "rules_docker-0.16.0",
    urls = [
        "https://github.com/bazelbuild/rules_docker/releases/download/v0.16.0/rules_docker-v0.16.0.tar.gz",
        "https://storage.googleapis.com/builddeps/95d39fd84ff4474babaf190450ee034d958202043e366b9fc38f438c9e6c3334",
    ],
)

http_archive(
    name = "com_github_ash2k_bazel_tools",
    sha256 = "46fdbc00930c8dc9d84690b5bd94db6b4683b061199967d2cda1cfbda8f02c49",
    strip_prefix = "bazel-tools-19b174803c0db1a01e77f10fa2079c35f54eed6e",
    urls = [
        "https://github.com/ash2k/bazel-tools/archive/19b174803c0db1a01e77f10fa2079c35f54eed6e.zip",
        "https://storage.googleapis.com/builddeps/46fdbc00930c8dc9d84690b5bd94db6b4683b061199967d2cda1cfbda8f02c49",
    ],
)

# Disk images
http_file(
    name = "alpine_image",
    sha256 = "a90150589e493d5b7e87297056b6e124d8af1b91fa2eb92bab61a839839e287b",
    urls = [
        "https://dl-cdn.alpinelinux.org/alpine/v3.16/releases/x86_64/alpine-virt-3.16.3-x86_64.iso",
        "https://storage.googleapis.com/builddeps/a90150589e493d5b7e87297056b6e124d8af1b91fa2eb92bab61a839839e287b",
    ],
)

http_file(
    name = "alpine_image_aarch64",
    sha256 = "f3510fa675a6480a5f86b3325e97ca764368a8138d95fc4ba2efaebb41f8e325",
    urls = [
        "https://dl-cdn.alpinelinux.org/alpine/v3.16/releases/aarch64/alpine-virt-3.16.3-aarch64.iso",
        "https://storage.googleapis.com/builddeps/f3510fa675a6480a5f86b3325e97ca764368a8138d95fc4ba2efaebb41f8e325",
    ],
)

http_file(
    name = "cirros_image",
    sha256 = "932fcae93574e242dc3d772d5235061747dfe537668443a1f0567d893614b464",
    urls = [
        "https://download.cirros-cloud.net/0.5.2/cirros-0.5.2-x86_64-disk.img",
        "https://storage.googleapis.com/builddeps/932fcae93574e242dc3d772d5235061747dfe537668443a1f0567d893614b464",
    ],
)

http_file(
    name = "cirros_image_aarch64",
    sha256 = "889c1117647b3b16cfc47957931c6573bf8e755fc9098fdcad13727b6c9f2629",
    urls = [
        "https://download.cirros-cloud.net/0.5.2/cirros-0.5.2-aarch64-disk.img",
        "https://storage.googleapis.com/builddeps/889c1117647b3b16cfc47957931c6573bf8e755fc9098fdcad13727b6c9f2629",
    ],
)

http_file(
    name = "virtio_win_image",
    sha256 = "b8a4bc66835c43091a85d35a10b59bd8b1b62b55ea9f02ec754f68bd32e82c0e",
    urls = [
        "https://fedorapeople.org/groups/virt/virtio-win/direct-downloads/archive-virtio/virtio-win-0.1.217-1/virtio-win-0.1.217.iso",
        "https://storage.googleapis.com/builddeps/b8a4bc66835c43091a85d35a10b59bd8b1b62b55ea9f02ec754f68bd32e82c0e",
    ],
)

http_archive(
    name = "bazeldnf",
    sha256 = "fb24d80ad9edad0f7bd3000e8cffcfbba89cc07e495c47a7d3b1f803bd527a40",
    urls = [
        "https://github.com/rmohr/bazeldnf/releases/download/v0.5.9/bazeldnf-v0.5.9.tar.gz",
    ],
)

load(
    "@io_bazel_rules_go//go:deps.bzl",
    "go_register_toolchains",
    "go_rules_dependencies",
)
load("@bazeldnf//:deps.bzl", "bazeldnf_dependencies", "rpm")

go_rules_dependencies()

go_register_toolchains(
    go_version = "1.21.8",
    nogo = "@//:nogo_vet",
)

load("@com_github_ash2k_bazel_tools//goimports:deps.bzl", "goimports_dependencies")

goimports_dependencies()

load(
    "@bazel_gazelle//:deps.bzl",
    "gazelle_dependencies",
    "go_repository",
)

gazelle_dependencies()

load("@com_github_bazelbuild_buildtools//buildifier:deps.bzl", "buildifier_dependencies")

buildifier_dependencies()

bazeldnf_dependencies()

load(
    "@bazel_tools//tools/build_defs/repo:git.bzl",
    "git_repository",
)

# Winrmcli dependencies
go_repository(
    name = "com_github_masterzen_winrmcli",
    commit = "c85a68ee8b6e3ac95af2a5fd62d2f41c9e9c5f32",
    importpath = "github.com/masterzen/winrm-cli",
)

# Winrmcp deps
go_repository(
    name = "com_github_packer_community_winrmcp",
    commit = "c76d91c1e7db27b0868c5d09e292bb540616c9a2",
    importpath = "github.com/packer-community/winrmcp",
)

go_repository(
    name = "com_github_masterzen_winrm_cli",
    commit = "6f0c57dee4569c04f64c44c335752b415e5d73a7",
    importpath = "github.com/masterzen/winrm-cli",
)

go_repository(
    name = "com_github_masterzen_winrm",
    commit = "1d17eaf15943ca3554cdebb3b1b10aaa543a0b7e",
    importpath = "github.com/masterzen/winrm",
)

go_repository(
    name = "com_github_nu7hatch_gouuid",
    commit = "179d4d0c4d8d407a32af483c2354df1d2c91e6c3",
    importpath = "github.com/nu7hatch/gouuid",
)

go_repository(
    name = "com_github_dylanmei_iso8601",
    commit = "2075bf119b58e5576c6ed9f867b8f3d17f2e54d4",
    importpath = "github.com/dylanmei/iso8601",
)

go_repository(
    name = "com_github_gofrs_uuid",
    commit = "abfe1881e60ef34074c1b8d8c63b42565c356ed6",
    importpath = "github.com/gofrs/uuid",
)

go_repository(
    name = "com_github_christrenkamp_goxpath",
    commit = "c5096ec8773dd9f554971472081ddfbb0782334e",
    importpath = "github.com/ChrisTrenkamp/goxpath",
)

go_repository(
    name = "com_github_azure_go_ntlmssp",
    commit = "4a21cbd618b459155f8b8ee7f4491cd54f5efa77",
    importpath = "github.com/Azure/go-ntlmssp",
)

go_repository(
    name = "com_github_masterzen_simplexml",
    commit = "31eea30827864c9ab643aa5a0d5b2d4988ec8409",
    importpath = "github.com/masterzen/simplexml",
)

go_repository(
    name = "org_golang_x_crypto",
    commit = "4def268fd1a49955bfb3dda92fe3db4f924f2285",
    importpath = "golang.org/x/crypto",
)

# override rules_docker issue with this dependency
# rules_docker 0.16 uses 0.1.4, let's grab by commit
go_repository(
    name = "com_github_google_go_containerregistry",
    commit = "8a2841911ffee4f6892ca0083e89752fb46c48dd",  # v0.1.4
    importpath = "github.com/google/go-containerregistry",
)

# bazel docker rules
load(
    "@io_bazel_rules_docker//container:container.bzl",
    "container_image",
    "container_pull",
)
load(
    "@io_bazel_rules_docker//repositories:repositories.bzl",
    container_repositories = "repositories",
)

container_repositories()

load("@io_bazel_rules_docker//repositories:deps.bzl", container_deps = "deps")

container_deps()

# Pull go_image_base
container_pull(
    name = "go_image_base",
    digest = "sha256:9d6c97c160bff0f78a443b583811dd0c8dde5c5086fe8fd2aaf2c23ee7e9590a",
    registry = "gcr.io",
    repository = "distroless/base-debian12",
)

container_pull(
    name = "go_image_base_aarch64",
    digest = "sha256:b251ebd844116427f92523668ca5e9f8d803e479eef44705b62090176d5e8cc7",
    registry = "gcr.io",
    repository = "distroless/base-debian12",
)

# Pull nfs-server image
# WARNING: please update any automated process to push this image to quay.io
# instead of index.docker.io
# TODO build nfs-server for multi-arch
container_pull(
    name = "nfs-server",
    digest = "sha256:8c1fa882dddb2885c4152e9ce632c466f4b8dce29339455e9b6bfe71f0a3d3ef",
    registry = "quay.io",
    repository = "kubevirtci/nfs-ganesha",  # see https://github.com/slintes/docker-nfs-ganesha
)

container_pull(
    name = "nfs-server_aarch64",
    digest = "sha256:8c1fa882dddb2885c4152e9ce632c466f4b8dce29339455e9b6bfe71f0a3d3ef",
    registry = "quay.io",
    repository = "kubevirtci/nfs-ganesha",  # see https://github.com/slintes/docker-nfs-ganesha
)

# Pull fedora container-disk preconfigured with ci tooling
# like stress and qemu guest agent pre-configured
# TODO build fedora_with_test_tooling for multi-arch
container_pull(
    name = "fedora_with_test_tooling",
    digest = "sha256:85f7bb99624422dc45b2c203d520a06bfce7a760ef831aafbf0e2bf2b92ebcf4",
    registry = "quay.io",
    repository = "kubevirtci/fedora-with-test-tooling",
)

container_pull(
    name = "alpine_with_test_tooling",
    digest = "sha256:abd71660edffc355520239e8910debfa7491516ee35240f23bba378d9095410c",
    registry = "quay.io",
    repository = "kubevirtci/alpine-with-test-tooling-container-disk",
    tag = "2211021552-8cca8c0",
)

container_pull(
    name = "fedora_with_test_tooling_aarch64",
    digest = "sha256:f5bcb56c8c3ce6f0801aa897db4691950235e7676d1ae22c64b088def4196701",
    registry = "quay.io",
    repository = "kubevirtci/fedora-with-test-tooling",
)

container_pull(
    name = "alpine-ext-kernel-boot-demo-container-base",
    digest = "sha256:a2ddb2f568bf3814e594a14bc793d5a655a61d5983f3561d60d02afa7bbc56b4",
    registry = "quay.io",
    repository = "kubevirt/alpine-ext-kernel-boot-demo",
)

# TODO build fedora_realtime for multi-arch
container_pull(
    name = "fedora_realtime",
    digest = "sha256:437f4e02986daf0058239f4a282d32304dcac629d5d1b4c75a74025f1ce22811",
    registry = "quay.io",
    repository = "kubevirt/fedora-realtime-container-disk",
)

load(
    "@io_bazel_rules_docker//go:image.bzl",
    _go_image_repos = "repositories",
)

_go_image_repos()

http_archive(
    name = "io_bazel_rules_container_rpm",
    sha256 = "151261f1b81649de6e36f027c945722bff31176f1340682679cade2839e4b1e1",
    strip_prefix = "rules_container_rpm-0.0.5",
    urls = [
        "https://github.com/rmohr/rules_container_rpm/archive/v0.0.5.tar.gz",
        "https://storage.googleapis.com/builddeps/151261f1b81649de6e36f027c945722bff31176f1340682679cade2839e4b1e1",
    ],
)

http_archive(
    name = "libguestfs-appliance",
    sha256 = "124d6325a799e958843be4818ef2c32661755be1c56e519665779948861b04f6",
    urls = [
        "https://storage.googleapis.com/kubevirt-prow/devel/release/kubevirt/libguestfs-appliance/libguestfs-appliance-1.48.4-qcow2-linux-5.14.0-183-centos9.tar.xz",
    ],
)

# Get container-disk-v1alpha RPM's
http_file(
    name = "qemu-img",
    sha256 = "669250ad47aad5939cf4d1b88036fd95a94845d8e0bbdb05e933f3d2fe262fea",
    urls = ["https://storage.googleapis.com/builddeps/669250ad47aad5939cf4d1b88036fd95a94845d8e0bbdb05e933f3d2fe262fea"],
)

# some repos which are not part of go_rules anymore
go_repository(
    name = "com_github_golang_glog",
    importpath = "github.com/golang/glog",
    sum = "h1:VKtxabqXZkF25pY9ekfRL6a582T4P37/31XEstQ5p58=",
    version = "v0.0.0-20160126235308-23def4e6c14b",
)

go_repository(
    name = "org_golang_google_grpc",
    importpath = "google.golang.org/grpc",
    sum = "h1:M5a8xTlYTxwMn5ZFkwhRabsygDY5G8TYLyQDBxJNAxE=",
    version = "v1.30.0",
)

go_repository(
    name = "org_golang_x_net",
    importpath = "golang.org/x/net",
    sum = "h1:oWX7TPOiFAMXLq8o0ikBYfCJVlRHBcsciT5bXOrH628=",
    version = "v0.0.0-20190311183353-d8887717615a",
)

go_repository(
    name = "org_golang_x_text",
    importpath = "golang.org/x/text",
    sum = "h1:g61tztE5qeGQ89tm6NTjjM9VPIm088od1l6aSorWRWg=",
    version = "v0.3.0",
)

register_toolchains("//:py_toolchain")

go_repository(
    name = "org_golang_x_mod",
    build_file_generation = "on",
    build_file_proto_mode = "disable",
    importpath = "golang.org/x/mod",
    sum = "h1:RM4zey1++hCTbCVQfnWeKs9/IEsaBLA8vTkd0WVtmH4=",
    version = "v0.3.0",
)

go_repository(
    name = "org_golang_x_xerrors",
    build_file_generation = "on",
    build_file_proto_mode = "disable",
    importpath = "golang.org/x/xerrors",
    sum = "h1:go1bK/D/BFZV2I8cIQd1NKEZ+0owSTG1fDTci4IqFcE=",
    version = "v0.0.0-20200804184101-5ec99f83aff1",
)

rpm(
    name = "acl-0__2.3.1-3.el9.aarch64",
    sha256 = "bfc8bc6339d8c51ae94f7f7cfbf6f3bc984baf8c82b1d411d1bbb3c67e645835",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/a/acl-2.3.1-3.el9.aarch64.rpm",
    ],
)

rpm(
    name = "acl-0__2.3.1-3.el9.x86_64",
    sha256 = "2e2219e4bcc328f3063aa51dbb7e69e74d9174cfe210227cf6801a82f6569954",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/a/acl-2.3.1-3.el9.x86_64.rpm",
    ],
)

rpm(
    name = "adobe-source-code-pro-fonts-0__2.030.1.050-12.el9.1.x86_64",
    sha256 = "a2ae30876e45d49b94caad29fdc085e2f7b0261daf9c95a1540c2823988e3cce",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/a/adobe-source-code-pro-fonts-2.030.1.050-12.el9.1.noarch.rpm",
    ],
)

rpm(
    name = "alternatives-0__1.24-1.el9.aarch64",
    sha256 = "4b809cb938b9c32eff0d6cf70e6689f2e5eef57ddec3ff7280fb611315b632c8",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/a/alternatives-1.24-1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "alternatives-0__1.24-1.el9.x86_64",
    sha256 = "801468c002aedd7fe1176c09a4cfda1f79d028a7907c404266ed652bcd6bb8a6",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/a/alternatives-1.24-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "audit-libs-0__3.0.7-104.el9.aarch64",
    sha256 = "fdae4609d170728ae9a509b303768f1834e6f1361c1d07c58544dbe7d4fb9a7f",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/a/audit-libs-3.0.7-104.el9.aarch64.rpm",
    ],
)

rpm(
    name = "audit-libs-0__3.0.7-104.el9.x86_64",
    sha256 = "4ecc2ccb3aff7275c01ffa17844be8cfa35c23dda1628008fdf22c3271833ec7",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/a/audit-libs-3.0.7-104.el9.x86_64.rpm",
    ],
)

rpm(
    name = "augeas-libs-0__1.13.0-5.el9.x86_64",
    sha256 = "2a949b27260999972700e7689f6d4f7a034f45c0de5739a36858cbed7d27dca4",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/a/augeas-libs-1.13.0-5.el9.x86_64.rpm",
    ],
)

rpm(
    name = "basesystem-0__11-13.el9.0.1.aarch64",
    sha256 = "9f707e8d1046381c9b4a4df6a6674327df6ffe0298d48e1750972212c97aafad",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/b/basesystem-11-13.el9.0.1.noarch.rpm",
    ],
)

rpm(
    name = "basesystem-0__11-13.el9.0.1.x86_64",
    sha256 = "9f707e8d1046381c9b4a4df6a6674327df6ffe0298d48e1750972212c97aafad",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/b/basesystem-11-13.el9.0.1.noarch.rpm",
    ],
)

rpm(
    name = "bash-0__5.1.8-6.el9_1.aarch64",
    sha256 = "7cdd44b2c686c719f1713d7f558694850417ba9b7104c26653fba8d50ac21ee8",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/b/bash-5.1.8-6.el9_1.aarch64.rpm",
    ],
)

rpm(
    name = "bash-0__5.1.8-6.el9_1.x86_64",
    sha256 = "7df53740511c98bf16b170c321352d3202987696cedbebd3d4a25ca44d4eff32",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/b/bash-5.1.8-6.el9_1.x86_64.rpm",
    ],
)

rpm(
    name = "binutils-0__2.35.2-42.el9_3.1.aarch64",
    sha256 = "728ce066129a9f008d0b5491384c4d7d43b912d56117934a9e5c693263a021a7",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/b/binutils-2.35.2-42.el9_3.1.aarch64.rpm",
    ],
)

rpm(
    name = "binutils-0__2.35.2-42.el9_3.1.x86_64",
    sha256 = "b846b05a69eb0ef08191d358d1effa8c76011a9e3452247d281fe8baf092e946",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/b/binutils-2.35.2-42.el9_3.1.x86_64.rpm",
    ],
)

rpm(
    name = "binutils-gold-0__2.35.2-42.el9_3.1.aarch64",
    sha256 = "e0f2ecfab36e762a754926a4d72cd38b4055355668a10015248a801f1a6e748e",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/b/binutils-gold-2.35.2-42.el9_3.1.aarch64.rpm",
    ],
)

rpm(
    name = "binutils-gold-0__2.35.2-42.el9_3.1.x86_64",
    sha256 = "1aeb0ea29e44717e8e09b79af779a4fcebdc6b0ffcada76206f4e592d087e451",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/b/binutils-gold-2.35.2-42.el9_3.1.x86_64.rpm",
    ],
)

rpm(
    name = "bzip2-0__1.0.8-8.el9.aarch64",
    sha256 = "33231db3f39bda7d6a7c9119a8760841f893686fa0e85760cc84d0e47db2a522",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/b/bzip2-1.0.8-8.el9.aarch64.rpm",
    ],
)

rpm(
    name = "bzip2-0__1.0.8-8.el9.x86_64",
    sha256 = "3646c3d3a77ce0d536dc5bd3926cdd9bd1b09d4a5b430d08bad985f22e9604c5",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/b/bzip2-1.0.8-8.el9.x86_64.rpm",
    ],
)

rpm(
    name = "bzip2-libs-0__1.0.8-8.el9.aarch64",
    sha256 = "6cb0a431273433308d933ae9d73ca3dc014004b7c97aac6859593bc3e0312646",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/b/bzip2-libs-1.0.8-8.el9.aarch64.rpm",
    ],
)

rpm(
    name = "bzip2-libs-0__1.0.8-8.el9.x86_64",
    sha256 = "9d88efca766d67129bf9e94f4fed072e6faf74fb8d905b1f37a5eefddcb248b2",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/b/bzip2-libs-1.0.8-8.el9.x86_64.rpm",
    ],
)

rpm(
    name = "ca-certificates-0__2023.2.60_v7.0.306-90.1.el9_2.aarch64",
    sha256 = "0c7bdf3ffc5f6d7e253921a58cf39ad8fae8ec353bb40fc3c0f412dddd89c9f9",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/c/ca-certificates-2023.2.60_v7.0.306-90.1.el9_2.noarch.rpm",
    ],
)

rpm(
    name = "ca-certificates-0__2023.2.60_v7.0.306-90.1.el9_2.x86_64",
    sha256 = "0c7bdf3ffc5f6d7e253921a58cf39ad8fae8ec353bb40fc3c0f412dddd89c9f9",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/c/ca-certificates-2023.2.60_v7.0.306-90.1.el9_2.noarch.rpm",
    ],
)

rpm(
    name = "capstone-0__4.0.2-10.el9.aarch64",
    sha256 = "45b0decca0b39dd5023d07324fb5cab2b5558d8dc083583b42d04a169abac2da",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/c/capstone-4.0.2-10.el9.aarch64.rpm",
    ],
)

rpm(
    name = "capstone-0__4.0.2-10.el9.x86_64",
    sha256 = "64bf1e7b9165e88d94499fd96d101e7a97007f5a4131d4c4860fcbc2464a2f9c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/c/capstone-4.0.2-10.el9.x86_64.rpm",
    ],
)

rpm(
    name = "coreutils-single-0__8.32-34.el9.aarch64",
    sha256 = "830215feedfd9e0a36fb0298ffbe3ff4ed09e280739dd769846f96e8ec825d8e",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/c/coreutils-single-8.32-34.el9.aarch64.rpm",
    ],
)

rpm(
    name = "coreutils-single-0__8.32-34.el9.x86_64",
    sha256 = "d90c4ef3da9e453a13847efe8c2212db7783e2a690c86f847fb3f4a9e182580d",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/c/coreutils-single-8.32-34.el9.x86_64.rpm",
    ],
)

rpm(
    name = "cpp-0__11.4.1-2.1.el9.aarch64",
    sha256 = "d3e6fc278099dc6d2bec457e910e1af4d7b12cfbb7d4f8a19482dac49394e509",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/c/cpp-11.4.1-2.1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "cpp-0__11.4.1-2.1.el9.x86_64",
    sha256 = "c198df693f5bb8f003fc3609add898bba721f514feea940ea6cc211890d30c0b",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/c/cpp-11.4.1-2.1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "cracklib-0__2.9.6-27.el9.aarch64",
    sha256 = "6fc09c48f1aeab91a14ec82167b60c7252412d6c2776f66007968c359831162c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/c/cracklib-2.9.6-27.el9.aarch64.rpm",
    ],
)

rpm(
    name = "cracklib-0__2.9.6-27.el9.x86_64",
    sha256 = "05abbfe7039c63fd1f3e9c216beec6edfda60568ee2f12e203f126dd2b618877",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/c/cracklib-2.9.6-27.el9.x86_64.rpm",
    ],
)

rpm(
    name = "cracklib-dicts-0__2.9.6-27.el9.aarch64",
    sha256 = "7b71caee8a5ed5d399ed8ec20848fa3015a361c94156435afc20d8814815f8f4",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/c/cracklib-dicts-2.9.6-27.el9.aarch64.rpm",
    ],
)

rpm(
    name = "cracklib-dicts-0__2.9.6-27.el9.x86_64",
    sha256 = "5ba79a7ce247aa40f1f9d95a917c054210a931070d059ebf1614a34461b5432c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/c/cracklib-dicts-2.9.6-27.el9.x86_64.rpm",
    ],
)

rpm(
    name = "crypto-policies-0__20230731-1.git94f0e2c.el9_3.1.aarch64",
    sha256 = "7977f446dbaffe68803dddb0b5f590f9981f32a2229a22f085565aa1643146d3",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/c/crypto-policies-20230731-1.git94f0e2c.el9_3.1.noarch.rpm",
    ],
)

rpm(
    name = "crypto-policies-0__20230731-1.git94f0e2c.el9_3.1.x86_64",
    sha256 = "7977f446dbaffe68803dddb0b5f590f9981f32a2229a22f085565aa1643146d3",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/c/crypto-policies-20230731-1.git94f0e2c.el9_3.1.noarch.rpm",
    ],
)

rpm(
    name = "curl-minimal-0__7.76.1-26.el9_3.3.aarch64",
    sha256 = "39a1bac615f2344e3e4697cd0986aa37483607f1fcd5b2e8cdef3dee80b402d1",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/c/curl-minimal-7.76.1-26.el9_3.3.aarch64.rpm",
    ],
)

rpm(
    name = "curl-minimal-0__7.76.1-26.el9_3.3.x86_64",
    sha256 = "8103ea79813b3fd65d7d31ae1ad80358b572125e1d3d9e66963a61c67ce91a52",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/c/curl-minimal-7.76.1-26.el9_3.3.x86_64.rpm",
    ],
)

rpm(
    name = "cyrus-sasl-0__2.1.27-21.el9.aarch64",
    sha256 = "137cfdc8c623e526622fe423b319baf4b8bcb783ad4966ddf2b3307196b5b815",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/c/cyrus-sasl-2.1.27-21.el9.aarch64.rpm",
    ],
)

rpm(
    name = "cyrus-sasl-0__2.1.27-21.el9.x86_64",
    sha256 = "d8345d8cb2c4438a9d2478ca7d6f10d9cd90efe7c0876f58781a58f32a99fdf8",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/c/cyrus-sasl-2.1.27-21.el9.x86_64.rpm",
    ],
)

rpm(
    name = "cyrus-sasl-gssapi-0__2.1.27-21.el9.aarch64",
    sha256 = "c08a4323f66a397a3ce1ce8a790bb7a29431ea5dfbe071b7193c60ac634da857",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/c/cyrus-sasl-gssapi-2.1.27-21.el9.aarch64.rpm",
    ],
)

rpm(
    name = "cyrus-sasl-gssapi-0__2.1.27-21.el9.x86_64",
    sha256 = "4a2ca27f2781b4134589f2da8e09ed60375a18cb84d8eabb0339f44eafb9ccd5",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/c/cyrus-sasl-gssapi-2.1.27-21.el9.x86_64.rpm",
    ],
)

rpm(
    name = "cyrus-sasl-lib-0__2.1.27-21.el9.aarch64",
    sha256 = "f413dd81e101695270414c32ed757d11f58b4ac6876f2edbe5c7f7c11b84e41c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/c/cyrus-sasl-lib-2.1.27-21.el9.aarch64.rpm",
    ],
)

rpm(
    name = "cyrus-sasl-lib-0__2.1.27-21.el9.x86_64",
    sha256 = "997880c9126e9eceba7cbab49dfd0b85cacab30af214637ae5d3ad728d26d921",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/c/cyrus-sasl-lib-2.1.27-21.el9.x86_64.rpm",
    ],
)

rpm(
    name = "daxctl-libs-0__71.1-8.el9.x86_64",
    sha256 = "4dbd78c1b6e5d8f0f3ddae14b8b9c1f838d4527684153b7a4987ca177c6df3ec",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/d/daxctl-libs-71.1-8.el9.x86_64.rpm",
    ],
)

rpm(
    name = "dbus-1__1.12.20-8.el9.aarch64",
    sha256 = "b3bde1dd40048ed14f0e42343ff0979e589a41b0954b89f8a23d57892d688106",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/d/dbus-1.12.20-8.el9.aarch64.rpm",
    ],
)

rpm(
    name = "dbus-1__1.12.20-8.el9.x86_64",
    sha256 = "f9ab612861c66de02ad73a0ffb56b2f83b71de2326ea595ffeac47eea517e18f",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/d/dbus-1.12.20-8.el9.x86_64.rpm",
    ],
)

rpm(
    name = "dbus-broker-0__28-7.el9.aarch64",
    sha256 = "d43da2ba4cdef5a08f6d5598aaf4c315576cf135331ecedb33880b9165311fcd",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/d/dbus-broker-28-7.el9.aarch64.rpm",
    ],
)

rpm(
    name = "dbus-broker-0__28-7.el9.x86_64",
    sha256 = "38f5e8dbd4aadcf568e06f0e353c6d9d0e2991e692e221c51c3a21717149aece",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/d/dbus-broker-28-7.el9.x86_64.rpm",
    ],
)

rpm(
    name = "dbus-common-1__1.12.20-8.el9.aarch64",
    sha256 = "1dd8709f43f63277d6305b2ef572cb091ef748ce1588a0bafc95866c397335b9",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/d/dbus-common-1.12.20-8.el9.noarch.rpm",
    ],
)

rpm(
    name = "dbus-common-1__1.12.20-8.el9.x86_64",
    sha256 = "1dd8709f43f63277d6305b2ef572cb091ef748ce1588a0bafc95866c397335b9",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/d/dbus-common-1.12.20-8.el9.noarch.rpm",
    ],
)

rpm(
    name = "dbus-libs-1__1.12.20-8.el9.aarch64",
    sha256 = "472aefc4bb2db327841c9c8fa3bc30f56dc5e00b0e77fac9c179e39ba7ad0146",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/d/dbus-libs-1.12.20-8.el9.aarch64.rpm",
    ],
)

rpm(
    name = "dbus-libs-1__1.12.20-8.el9.x86_64",
    sha256 = "ab81c1e16482f333aa285db120051b099b56661d4620f0f1af05f8e69126e97b",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/d/dbus-libs-1.12.20-8.el9.x86_64.rpm",
    ],
)

rpm(
    name = "device-mapper-9__1.02.195-3.el9.aarch64",
    sha256 = "356bba9324797b4fff05bc54954f525e466b6f2b88c8ba900584e0315ad6035e",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/d/device-mapper-1.02.195-3.el9.aarch64.rpm",
    ],
)

rpm(
    name = "device-mapper-9__1.02.195-3.el9.x86_64",
    sha256 = "5c747902760359247fbe21a9b83365f60b602d8edefaa7f71e39a7e7c8562c0b",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/d/device-mapper-1.02.195-3.el9.x86_64.rpm",
    ],
)

rpm(
    name = "device-mapper-libs-9__1.02.195-3.el9.aarch64",
    sha256 = "f263429d9fb316373bddfa883a694dd022a3ebcb43db445a101f2e37816c6afe",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/d/device-mapper-libs-1.02.195-3.el9.aarch64.rpm",
    ],
)

rpm(
    name = "device-mapper-libs-9__1.02.195-3.el9.x86_64",
    sha256 = "e77998dbc277001975f38acc61f43adb3c421cb4ccfcc67d80cb97e745261095",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/d/device-mapper-libs-1.02.195-3.el9.x86_64.rpm",
    ],
)

rpm(
    name = "device-mapper-multipath-libs-0__0.8.7-22.el9.aarch64",
    sha256 = "eb2df2f785661d6fd6834db4f3fa77c473216a42031a0b32ba9efe1a04d5f74c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/d/device-mapper-multipath-libs-0.8.7-22.el9.aarch64.rpm",
    ],
)

rpm(
    name = "device-mapper-multipath-libs-0__0.8.7-22.el9.x86_64",
    sha256 = "96e9c8407bcb6110f58a8be2eaa9f7a3937850b1da5f819454b4e63c97383861",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/d/device-mapper-multipath-libs-0.8.7-22.el9.x86_64.rpm",
    ],
)

rpm(
    name = "diffutils-0__3.7-12.el9.aarch64",
    sha256 = "df77e6cb59b73a1ff3d007c8011c689bf9bdbd416889bce8d65dc9855144e335",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/d/diffutils-3.7-12.el9.aarch64.rpm",
    ],
)

rpm(
    name = "diffutils-0__3.7-12.el9.x86_64",
    sha256 = "d3932991f5d9b1e5f6326e376cf77f3f676bbf0c5657b2ddf1013bfdb4738a69",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/d/diffutils-3.7-12.el9.x86_64.rpm",
    ],
)

rpm(
    name = "dmidecode-1__3.5-1.el9.x86_64",
    sha256 = "5a325966d2e3c89bf0f44fa32473884d7756ee2f64247d14a7ebb06ec1c3b65b",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/d/dmidecode-3.5-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "e2fsprogs-0__1.46.5-3.el9.aarch64",
    sha256 = "2f29ca8043227774c8aecd859ce2293fcd9848f1929309576be24a417984ce00",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/e/e2fsprogs-1.46.5-3.el9.aarch64.rpm",
    ],
)

rpm(
    name = "e2fsprogs-0__1.46.5-3.el9.x86_64",
    sha256 = "ba6659d0fed1cb23b1228d55b05c927a8f188be72a68509751c9199f34bf4c6f",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/e/e2fsprogs-1.46.5-3.el9.x86_64.rpm",
    ],
)

rpm(
    name = "e2fsprogs-libs-0__1.46.5-3.el9.aarch64",
    sha256 = "3577defde560591058bb0e14cbe76d0d647c08324095a1f0856a148191169d46",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/e/e2fsprogs-libs-1.46.5-3.el9.aarch64.rpm",
    ],
)

rpm(
    name = "e2fsprogs-libs-0__1.46.5-3.el9.x86_64",
    sha256 = "b9d969f84ac8c462ab64306c18bae99a94e62d981ae650a3f6c9c20b68760f10",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/e/e2fsprogs-libs-1.46.5-3.el9.x86_64.rpm",
    ],
)

rpm(
    name = "edk2-aarch64-0__20230524-4.el9_3.2.aarch64",
    sha256 = "a2e62895c4a69f7041a0b6997a9bffd01fe40046717b025471fef19e0b5df31b",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/e/edk2-aarch64-20230524-4.el9_3.2.noarch.rpm",
    ],
)

rpm(
    name = "edk2-ovmf-0__20230524-4.el9_3.2.x86_64",
    sha256 = "d847d851440fa471fb43f535bb9d49373a8a4d8b613634327995c03aef6f2aaf",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/e/edk2-ovmf-20230524-4.el9_3.2.noarch.rpm",
    ],
)

rpm(
    name = "elfutils-debuginfod-client-0__0.189-3.el9.aarch64",
    sha256 = "d562a25281725f7d95e74c2f40e4b5d62e52acdc4b1e5c505df0ccbb63c24e1e",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/e/elfutils-debuginfod-client-0.189-3.el9.aarch64.rpm",
    ],
)

rpm(
    name = "elfutils-debuginfod-client-0__0.189-3.el9.x86_64",
    sha256 = "e758158b34cce090ce41ac60b6542f6df41942a32437eb546990784f09c44c19",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/e/elfutils-debuginfod-client-0.189-3.el9.x86_64.rpm",
    ],
)

rpm(
    name = "elfutils-default-yama-scope-0__0.189-3.el9.aarch64",
    sha256 = "de1edccd6c01d8d7bc69590d11de385988b2d4036f0df92653e37381a6ee1dd0",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/e/elfutils-default-yama-scope-0.189-3.el9.noarch.rpm",
    ],
)

rpm(
    name = "elfutils-default-yama-scope-0__0.189-3.el9.x86_64",
    sha256 = "de1edccd6c01d8d7bc69590d11de385988b2d4036f0df92653e37381a6ee1dd0",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/e/elfutils-default-yama-scope-0.189-3.el9.noarch.rpm",
    ],
)

rpm(
    name = "elfutils-libelf-0__0.189-3.el9.aarch64",
    sha256 = "5133857ef04ca849e41996d7b6d5c4345935912bac49765fb537e9597ca6f2e4",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/e/elfutils-libelf-0.189-3.el9.aarch64.rpm",
    ],
)

rpm(
    name = "elfutils-libelf-0__0.189-3.el9.x86_64",
    sha256 = "2d61d3deaebbfc30e08003efc08c01eb24b2a4637446892cc56c053a29c241bf",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/e/elfutils-libelf-0.189-3.el9.x86_64.rpm",
    ],
)

rpm(
    name = "elfutils-libs-0__0.189-3.el9.aarch64",
    sha256 = "4e2ee96c0032e78845bb91c7e52a9c3e762a0fb1ea39c5836cf4d04892587538",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/e/elfutils-libs-0.189-3.el9.aarch64.rpm",
    ],
)

rpm(
    name = "elfutils-libs-0__0.189-3.el9.x86_64",
    sha256 = "62596104ee3d12f7781d3b3a89bf2d0bc1b68f742e7efe788478f4001706b2a9",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/e/elfutils-libs-0.189-3.el9.x86_64.rpm",
    ],
)

rpm(
    name = "ethtool-2__6.2-1.el9.aarch64",
    sha256 = "bab44089cf27fda7dceec226f7472819e882282a53de2ab360154da12ac02280",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/e/ethtool-6.2-1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "ethtool-2__6.2-1.el9.x86_64",
    sha256 = "856da319a7ef9703bfe3d29ad19053b94b4b3ce67155981acf6a279958c555a8",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/e/ethtool-6.2-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "expat-0__2.5.0-1.el9_3.1.aarch64",
    sha256 = "cf194936dbce6690724b6f8666417240ff48081a320e1e74ffcf85e70cc360cc",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/e/expat-2.5.0-1.el9_3.1.aarch64.rpm",
    ],
)

rpm(
    name = "expat-0__2.5.0-1.el9_3.1.x86_64",
    sha256 = "c4f427ff2382232ac18ee28f2513811e968d0e91967bd66fcc045dcb03725772",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/e/expat-2.5.0-1.el9_3.1.x86_64.rpm",
    ],
)

rpm(
    name = "filesystem-0__3.16-2.el9.aarch64",
    sha256 = "58be72c7740ac788f81828c28af917fae95e8f769fbe7ba8eb5290f98c4023cd",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/f/filesystem-3.16-2.el9.aarch64.rpm",
    ],
)

rpm(
    name = "filesystem-0__3.16-2.el9.x86_64",
    sha256 = "211e67cf31d096ca3f4bbddcdf6116afa821997e61e9c07d29c3c6e53546e697",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/f/filesystem-3.16-2.el9.x86_64.rpm",
    ],
)

rpm(
    name = "findutils-1__4.8.0-6.el9.aarch64",
    sha256 = "8ddd95c3c91b52ec38cf81be7e0dcc1dd8fdfb475da78f585db14b456593b3c2",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/f/findutils-4.8.0-6.el9.aarch64.rpm",
    ],
)

rpm(
    name = "findutils-1__4.8.0-6.el9.x86_64",
    sha256 = "7d4a18cf3517b7337b3cb19053972b20ea645878cf99e471e6c4aea5394522be",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/f/findutils-4.8.0-6.el9.x86_64.rpm",
    ],
)

rpm(
    name = "fonts-filesystem-1__2.0.5-7.el9.1.x86_64",
    sha256 = "99d15efb904085c385292eb10bb3c84a3f16d3cedb2c2b871756f9036e77c7bc",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/f/fonts-filesystem-2.0.5-7.el9.1.noarch.rpm",
    ],
)

rpm(
    name = "fuse-0__2.9.9-15.el9.x86_64",
    sha256 = "639d5e4cc247426421bc87eeee5c7263250337af92d0694a1893ec9a5555c8ff",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/f/fuse-2.9.9-15.el9.x86_64.rpm",
    ],
)

rpm(
    name = "fuse-common-0__3.10.2-6.el9.x86_64",
    sha256 = "750cd3d933b455c89a2acf239acc220858ceed3b872804c4f53dcb4f7de56c40",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/f/fuse-common-3.10.2-6.el9.x86_64.rpm",
    ],
)

rpm(
    name = "fuse-libs-0__2.9.9-15.el9.aarch64",
    sha256 = "6afc0c4f0ead22dc457766d9f38c7283d9abc326a1c59919fafc3d33ab85b470",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/f/fuse-libs-2.9.9-15.el9.aarch64.rpm",
    ],
)

rpm(
    name = "fuse-libs-0__2.9.9-15.el9.x86_64",
    sha256 = "e915392c1380b3c75c43e5ebfa1bff21a4d280aa2f2417915b92a04829406896",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/f/fuse-libs-2.9.9-15.el9.x86_64.rpm",
    ],
)

rpm(
    name = "gawk-0__5.1.0-6.el9.aarch64",
    sha256 = "c831415c883ab8ecd6d62373cea563c73042d06463c91e6645f82984eeb12c74",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/g/gawk-5.1.0-6.el9.aarch64.rpm",
    ],
)

rpm(
    name = "gawk-0__5.1.0-6.el9.x86_64",
    sha256 = "eaca68b315d6c2ef5ec30deaf9b7c38401e2ed0169972d158fd88b917e8a47dc",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/g/gawk-5.1.0-6.el9.x86_64.rpm",
    ],
)

rpm(
    name = "gcc-0__11.4.1-2.1.el9.aarch64",
    sha256 = "852f2d620085280e7f738e26f0f46d6ae1ff3168aa503eb19e73e3fed94f9fb7",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/g/gcc-11.4.1-2.1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "gcc-0__11.4.1-2.1.el9.x86_64",
    sha256 = "157b93f22c2a2898cee246440044922979c9efffbe07e66d496e8e5bc022d354",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/g/gcc-11.4.1-2.1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "gdbm-libs-1__1.19-4.el9.aarch64",
    sha256 = "ec0bfbc439f8c8a02a72517dcaea3d0798e987524c24c7930d279096cc200ede",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/g/gdbm-libs-1.19-4.el9.aarch64.rpm",
    ],
)

rpm(
    name = "gdbm-libs-1__1.19-4.el9.x86_64",
    sha256 = "da032f6a47afb847153322df72e8d01d239e4481ac1750d195cf396393d11066",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/g/gdbm-libs-1.19-4.el9.x86_64.rpm",
    ],
)

rpm(
    name = "gettext-0__0.21-8.el9.aarch64",
    sha256 = "e881fae8a60986ab109f94e9b3012d00d4954b9b8d5345825ceddbd0e13ca436",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/g/gettext-0.21-8.el9.aarch64.rpm",
    ],
)

rpm(
    name = "gettext-0__0.21-8.el9.x86_64",
    sha256 = "e615a360a2c8bc196ea406d3768d3ebf3b5991057fe77a4ff777c2c0a8267d1e",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/g/gettext-0.21-8.el9.x86_64.rpm",
    ],
)

rpm(
    name = "gettext-libs-0__0.21-8.el9.aarch64",
    sha256 = "e8e7e273c70579e9e76bfa01fe95d61d46d982f2b663c893b021de6e6141d897",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/g/gettext-libs-0.21-8.el9.aarch64.rpm",
    ],
)

rpm(
    name = "gettext-libs-0__0.21-8.el9.x86_64",
    sha256 = "7ebafab783eb9d71de2282d2530a66b3b07df63c75bf087843b21e7e6a96b2ee",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/g/gettext-libs-0.21-8.el9.x86_64.rpm",
    ],
)

rpm(
    name = "glib-networking-0__2.68.3-3.el9.x86_64",
    sha256 = "fa9bec5c45cd1d4123f3e5e9793c592312d95dc50369740226969e69bd0e0ab0",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/g/glib-networking-2.68.3-3.el9.x86_64.rpm",
    ],
)

rpm(
    name = "glib2-0__2.68.4-11.el9.aarch64",
    sha256 = "cb50f885b22d6a0121960c3c95dfcb3d6564dcdec3ff0036a97e3c41857dca82",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/g/glib2-2.68.4-11.el9.aarch64.rpm",
    ],
)

rpm(
    name = "glib2-0__2.68.4-11.el9.x86_64",
    sha256 = "5792d6665dd65cf5a4d818c89ab4183521a60b9c54edc15d85089e065ae7a74c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/g/glib2-2.68.4-11.el9.x86_64.rpm",
    ],
)

rpm(
    name = "glibc-0__2.34-83.el9.12.aarch64",
    sha256 = "7f12429e230fa183f51c7aa5bc9dcc17956ddf2e82d193910ea2a2b5e89a3f1a",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/g/glibc-2.34-83.el9.12.aarch64.rpm",
    ],
)

rpm(
    name = "glibc-0__2.34-83.el9.12.x86_64",
    sha256 = "21a1f3479f63b84a26caa2c6aee93572f1d01cef3ee1c9020a259363d1960fde",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/g/glibc-2.34-83.el9.12.x86_64.rpm",
    ],
)

rpm(
    name = "glibc-common-0__2.34-83.el9.12.aarch64",
    sha256 = "b72a3128d3c311589a36d0e64cb7f4f6c9287e7ec4e180dcc5830aed54f6f6d7",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/g/glibc-common-2.34-83.el9.12.aarch64.rpm",
    ],
)

rpm(
    name = "glibc-common-0__2.34-83.el9.12.x86_64",
    sha256 = "8f540369ffdb0738761f8eb8b2c55bb237ae4414eb961606bfc98a34517506b7",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/g/glibc-common-2.34-83.el9.12.x86_64.rpm",
    ],
)

rpm(
    name = "glibc-devel-0__2.34-83.el9.12.aarch64",
    sha256 = "cf7382f0b2de018ce089a73f230cdd126bdfd2f19d6753f47c0ca7eafc6fab9f",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/g/glibc-devel-2.34-83.el9.12.aarch64.rpm",
    ],
)

rpm(
    name = "glibc-devel-0__2.34-83.el9.12.x86_64",
    sha256 = "ee3e9bebfdbe7c2e78f04d51b4ff0f713997613fa9fcf37b1062f75653f49974",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/g/glibc-devel-2.34-83.el9.12.x86_64.rpm",
    ],
)

rpm(
    name = "glibc-headers-0__2.34-83.el9.12.x86_64",
    sha256 = "1b0de3f0d57d1220ddcb93872390e0ea00b300dccf88e4f0af5989dce6d505c7",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/g/glibc-headers-2.34-83.el9.12.x86_64.rpm",
    ],
)

rpm(
    name = "glibc-minimal-langpack-0__2.34-83.el9.12.aarch64",
    sha256 = "83c149170f67ba4d058e8197fa55992fe19811ff6d4cd9325a276b4b277c9fca",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/g/glibc-minimal-langpack-2.34-83.el9.12.aarch64.rpm",
    ],
)

rpm(
    name = "glibc-minimal-langpack-0__2.34-83.el9.12.x86_64",
    sha256 = "62bdb619777ed04fc4ddf85e2ad429cb1fbb782a8998edaf555cd56509493b0c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/g/glibc-minimal-langpack-2.34-83.el9.12.x86_64.rpm",
    ],
)

rpm(
    name = "glibc-static-0__2.34-83.el9.12.aarch64",
    sha256 = "a7bdc3f1a5a675474fe82da7c8732acc98d8c1889336be24d62157a200bccb41",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/CRB/aarch64/os/Packages/g/glibc-static-2.34-83.el9.12.aarch64.rpm",
    ],
)

rpm(
    name = "glibc-static-0__2.34-83.el9.12.x86_64",
    sha256 = "0a35fa98d136e2d73d46699414e1299010e512fb00b23a085889877dc9b26011",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/CRB/x86_64/os/Packages/g/glibc-static-2.34-83.el9.12.x86_64.rpm",
    ],
)

rpm(
    name = "gmp-1__6.2.0-13.el9.aarch64",
    sha256 = "54f5999feb6a26c57616d64cc880dccb5e44723911f52b06a36311e389a568ce",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/g/gmp-6.2.0-13.el9.aarch64.rpm",
    ],
)

rpm(
    name = "gmp-1__6.2.0-13.el9.x86_64",
    sha256 = "ca72ae69218b96c43c82bdc35dd1078300692714db76d21c7f7dedd8268af799",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/g/gmp-6.2.0-13.el9.x86_64.rpm",
    ],
)

rpm(
    name = "gnupg2-0__2.3.3-4.el9.x86_64",
    sha256 = "be8e75ba0f2dacf5fde23d67b8939807696b48f33cc56881ffd656e136e5d8c8",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/g/gnupg2-2.3.3-4.el9.x86_64.rpm",
    ],
)

rpm(
    name = "gnutls-0__3.7.6-23.el9_3.4.aarch64",
    sha256 = "891428edf59bc9d61055b81d3f238de0b7677b1dc4e7927c966577ec5d094c36",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/g/gnutls-3.7.6-23.el9_3.4.aarch64.rpm",
    ],
)

rpm(
    name = "gnutls-0__3.7.6-23.el9_3.4.x86_64",
    sha256 = "16fbfba4283b8fa4b9d2e61b0d3aeb14c60e133c0de36be151779436243d55d1",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/g/gnutls-3.7.6-23.el9_3.4.x86_64.rpm",
    ],
)

rpm(
    name = "gnutls-dane-0__3.7.6-23.el9_3.4.aarch64",
    sha256 = "c094385412a27442e68de7ef6eb170f75bbddabc43f039e1a038bf13c5c3cb33",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/g/gnutls-dane-3.7.6-23.el9_3.4.aarch64.rpm",
    ],
)

rpm(
    name = "gnutls-dane-0__3.7.6-23.el9_3.4.x86_64",
    sha256 = "2eb5bd231005d7315d6d47affdfb947330b4e9974430fcf37ce50d6aa5b8ed5d",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/g/gnutls-dane-3.7.6-23.el9_3.4.x86_64.rpm",
    ],
)

rpm(
    name = "gnutls-utils-0__3.7.6-23.el9_3.4.aarch64",
    sha256 = "745b8d40606555ff04e3af54f2c01291dbf24dc1b15914dd153e9e5cc2d5c9f7",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/g/gnutls-utils-3.7.6-23.el9_3.4.aarch64.rpm",
    ],
)

rpm(
    name = "gnutls-utils-0__3.7.6-23.el9_3.4.x86_64",
    sha256 = "d44f23435c9c828ce2d4110cf9da4155984f9ec1a6fe870b413e7b99234c1481",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/g/gnutls-utils-3.7.6-23.el9_3.4.x86_64.rpm",
    ],
)

rpm(
    name = "gobject-introspection-0__1.68.0-11.el9.aarch64",
    sha256 = "53d9e22893411d62a68e11a56a9a2a2d56af3790838806c3df233caaeb968bc5",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/g/gobject-introspection-1.68.0-11.el9.aarch64.rpm",
    ],
)

rpm(
    name = "gobject-introspection-0__1.68.0-11.el9.x86_64",
    sha256 = "0bdb038fcd75126324e7a5a9c4ef18f487c1af764dfc9c600994ca1b04c605d3",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/g/gobject-introspection-1.68.0-11.el9.x86_64.rpm",
    ],
)

rpm(
    name = "grep-0__3.6-5.el9.aarch64",
    sha256 = "3c346bcb5b344c1dd3e68c9acd9fbbdd0300e3edfa331f5a4015c9d2ec95ff56",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/g/grep-3.6-5.el9.aarch64.rpm",
    ],
)

rpm(
    name = "grep-0__3.6-5.el9.x86_64",
    sha256 = "9c1beaec9264e08459f9097c9bd58aa6118293df47d6f07f8054054cc7c40544",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/g/grep-3.6-5.el9.x86_64.rpm",
    ],
)

rpm(
    name = "gsettings-desktop-schemas-0__40.0-6.el9.x86_64",
    sha256 = "f06da6ea5b8b8f1c97a79054474ced2b577731a96eaf5952ec8e670fa6aa2b83",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/g/gsettings-desktop-schemas-40.0-6.el9.x86_64.rpm",
    ],
)

rpm(
    name = "gssproxy-0__0.8.4-6.el9.x86_64",
    sha256 = "c7ea30d414a4bb495379ea80be7a2dc90b9eb327038eb8cf0f1f341c4b856b37",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/g/gssproxy-0.8.4-6.el9.x86_64.rpm",
    ],
)

rpm(
    name = "guestfs-tools-0__1.50.1-3.el9.x86_64",
    sha256 = "a3132aa8fd7269b12ae5949ca3a9be57a3be326ff6ccf297c713d79f0bfbf1b0",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/g/guestfs-tools-1.50.1-3.el9.x86_64.rpm",
    ],
)

rpm(
    name = "gzip-0__1.12-1.el9.aarch64",
    sha256 = "27c36893392e43bd2904ed4af6e6e92d5552c3ca4bd795a172b7419093d1f0f6",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/g/gzip-1.12-1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "gzip-0__1.12-1.el9.x86_64",
    sha256 = "cd22e3e9e04436c7463f0fd1cb44c816421fd62bd17336081a7453fd646a5c29",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/g/gzip-1.12-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "hexedit-0__1.6-1.el9.x86_64",
    sha256 = "ef81ba195321df0668abd24e96af92815a0f76a4b98dbf7558f21b7daebf5e8c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/h/hexedit-1.6-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "hivex-libs-0__1.3.21-3.el9.x86_64",
    sha256 = "3204db0bf220ffa122b53cf2c9d93972f837576de92ac730eb5b119abaad7092",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/h/hivex-libs-1.3.21-3.el9.x86_64.rpm",
    ],
)

rpm(
    name = "hwdata-0__0.348-9.11.el9.x86_64",
    sha256 = "4b8a9276c81624fde2fac347d634aea930bfd65208f1c4e0281590583f609e10",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/h/hwdata-0.348-9.11.el9.noarch.rpm",
    ],
)

rpm(
    name = "iproute-0__6.2.0-5.el9.aarch64",
    sha256 = "22533c1ac4547889c0acf6c038a314a066d68453142111ba51e6120f79d341a3",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/i/iproute-6.2.0-5.el9.aarch64.rpm",
    ],
)

rpm(
    name = "iproute-0__6.2.0-5.el9.x86_64",
    sha256 = "e1699f39ebbc39c3f10e948ede1fc1c966b3825ce5a54d05036ac79cb729806c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/i/iproute-6.2.0-5.el9.x86_64.rpm",
    ],
)

rpm(
    name = "iproute-tc-0__6.2.0-5.el9.aarch64",
    sha256 = "151dcb0590ff277b9b5ec3e016efc59383a12c2d1734076e3daee950075b3061",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/i/iproute-tc-6.2.0-5.el9.aarch64.rpm",
    ],
)

rpm(
    name = "iproute-tc-0__6.2.0-5.el9.x86_64",
    sha256 = "08d1391d23eff74e0d882b60c12f17d2b24bfb70639339a035d5822a9b406f7b",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/i/iproute-tc-6.2.0-5.el9.x86_64.rpm",
    ],
)

rpm(
    name = "iptables-libs-0__1.8.8-6.el9_1.aarch64",
    sha256 = "285a4b5271216bd8090f19a60f105a032070f904fd2f4e29fdf610b481ccaa8e",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/i/iptables-libs-1.8.8-6.el9_1.aarch64.rpm",
    ],
)

rpm(
    name = "iptables-libs-0__1.8.8-6.el9_1.x86_64",
    sha256 = "632d07e8c84edd023c4048b34cd97c2819e7611e7b9a0f9bfd819ba077d381fb",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/i/iptables-libs-1.8.8-6.el9_1.x86_64.rpm",
    ],
)

rpm(
    name = "iputils-0__20210202-9.el9.aarch64",
    sha256 = "4347585fd7cfabde46f64cb1ea28e9d93f69b924dab56c9cf121eb415e4c5177",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/i/iputils-20210202-9.el9.aarch64.rpm",
    ],
)

rpm(
    name = "iputils-0__20210202-9.el9.x86_64",
    sha256 = "ea8a95967cb5a4d37f8f09bba64f3b42457707af581c6ef507c45773c3d35f71",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/i/iputils-20210202-9.el9.x86_64.rpm",
    ],
)

rpm(
    name = "ipxe-roms-qemu-0__20200823-9.git4bd064de.el9.x86_64",
    sha256 = "571c22893e831cd0b2f5b79611684a4a9b2d7443444188a8b3d24d2f01115f38",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/i/ipxe-roms-qemu-20200823-9.git4bd064de.el9.noarch.rpm",
    ],
)

rpm(
    name = "jansson-0__2.14-1.el9.aarch64",
    sha256 = "19599e87e97cb2a712d84e0afa1af5edc9e77b4d269b917ca8bf751928954e6f",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/j/jansson-2.14-1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "jansson-0__2.14-1.el9.x86_64",
    sha256 = "14c82a4e792ab09724a7bd1b7921865d979a07b5eb99b6d11dd35e903dccc156",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/j/jansson-2.14-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "json-glib-0__1.6.6-1.el9.aarch64",
    sha256 = "1f6f5d394e90ad6302c705fa2ecea79fb0fc967f477c147a0e929aad0a6a3249",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/j/json-glib-1.6.6-1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "json-glib-0__1.6.6-1.el9.x86_64",
    sha256 = "8d1c6ba76414837da0f34d675512c71503b0ca6c2b3b1dfae6101e2a0b507cee",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/j/json-glib-1.6.6-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "kernel-headers-0__5.14.0-362.24.1.el9_3.0.1.aarch64",
    sha256 = "42076b42ccac052cf1494fb3e95b720c3d87b13fe79e99dffc9a28b602ba249b",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/k/kernel-headers-5.14.0-362.24.1.el9_3.0.1.aarch64.rpm",
    ],
)

rpm(
    name = "kernel-headers-0__5.14.0-362.24.1.el9_3.0.1.x86_64",
    sha256 = "d75c8cb621bee6a7c9aa6942b7985fbbda6ea467ed2b183275873bca67b346c3",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/k/kernel-headers-5.14.0-362.24.1.el9_3.0.1.x86_64.rpm",
    ],
)

rpm(
    name = "keyutils-0__1.6.3-1.el9.x86_64",
    sha256 = "1419a90e2ae9546603c2f04d9a7548f80322ff4574c5e77d9be52e51acb98abc",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/k/keyutils-1.6.3-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "keyutils-libs-0__1.6.3-1.el9.aarch64",
    sha256 = "7bdf0b6409a983dcb60006c2624a444e8465b12ad3bb8f47f22fa77b532ec74f",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/k/keyutils-libs-1.6.3-1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "keyutils-libs-0__1.6.3-1.el9.x86_64",
    sha256 = "347a9d44e0271c1ff6f511fe493e736b3d36fde683360ccc51c852ab91810b16",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/k/keyutils-libs-1.6.3-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "kmod-0__28-9.el9.x86_64",
    sha256 = "129be5c4daa104525e0b3fa8ee7dc9484ec8c02a83b01d885f264cc5e1189fd1",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/k/kmod-28-9.el9.x86_64.rpm",
    ],
)

rpm(
    name = "kmod-libs-0__28-9.el9.aarch64",
    sha256 = "a50db31a1941b21195ca3b23c77e17c2771f1e5bea8840480c2ba45fc217b5a6",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/k/kmod-libs-28-9.el9.aarch64.rpm",
    ],
)

rpm(
    name = "kmod-libs-0__28-9.el9.x86_64",
    sha256 = "3aaf53351ef79866f5ff5ace8f6984008846df834a6bde71297479eb6ea96727",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/k/kmod-libs-28-9.el9.x86_64.rpm",
    ],
)

rpm(
    name = "krb5-libs-0__1.21.1-1.el9.aarch64",
    sha256 = "8b3d6b1e789b7320256dc9e943e2aa81483292c7192d7cc757c0d1e2198ff123",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/k/krb5-libs-1.21.1-1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "krb5-libs-0__1.21.1-1.el9.x86_64",
    sha256 = "d3c9a2f4710e7c9020844286cae6a0db36c4061364f0d6ea2bef7c3edd347153",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/k/krb5-libs-1.21.1-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "less-0__590-3.el9_3.x86_64",
    sha256 = "2cac9b4523396e3b42f25707bc10554bdf1c13085ce03c80d49b0db32d9fecb1",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/less-590-3.el9_3.x86_64.rpm",
    ],
)

rpm(
    name = "libacl-0__2.3.1-3.el9.aarch64",
    sha256 = "192a8582963dae3e3730a5724378197a8f6c77801603c272a978a78003fa2a34",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libacl-2.3.1-3.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libacl-0__2.3.1-3.el9.x86_64",
    sha256 = "5b215deea69f4b6db45c47425741206e49e1f03dc754287e550bb898d62aa68e",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libacl-2.3.1-3.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libaio-0__0.3.111-13.el9.aarch64",
    sha256 = "9226b925be54956ee8a529f8e2edfa8a561cb0ec7af426ccd3bab7338c46f45a",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libaio-0.3.111-13.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libaio-0__0.3.111-13.el9.x86_64",
    sha256 = "f994942469a5554298c520148b4e8a66c3dd2d15bccf9b1aba34535b63edade6",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libaio-0.3.111-13.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libarchive-0__3.5.3-4.el9.aarch64",
    sha256 = "bcb0d36802b97bf2a69d91b091b907a68c0280fa6a3e4b72e91d8032281c0d22",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libarchive-3.5.3-4.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libarchive-0__3.5.3-4.el9.x86_64",
    sha256 = "966a1861544e02a311cce7e327b84775b91edcbc2f83676221fed3f23f9ad19d",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libarchive-3.5.3-4.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libasan-0__11.4.1-2.1.el9.aarch64",
    sha256 = "ca95bf45a211c7c84e531a52850f76dfe4ebd6fe5a2e9cec07faac8371fd5394",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/l/libasan-11.4.1-2.1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libassuan-0__2.5.5-3.el9.x86_64",
    sha256 = "5d5e555c9c4dfbd293acdc0ae739b41e635a2239a2c41ce11aafedd1d1ed54f4",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libassuan-2.5.5-3.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libatomic-0__11.4.1-2.1.el9.aarch64",
    sha256 = "f3d311b78c8386bbdf01ffc9879e8f93ebe36cb0cb8c3914d05e3759d8eea538",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libatomic-11.4.1-2.1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libattr-0__2.5.1-3.el9.aarch64",
    sha256 = "406cad9db484e7e7ee10f477844a7b7d0659b3ce904e53770c9e5f2347ef5a22",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libattr-2.5.1-3.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libattr-0__2.5.1-3.el9.x86_64",
    sha256 = "77742a1097d81c384b8c7529e3c049fb7de206b773ad230553be99ba5c9d9fc1",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libattr-2.5.1-3.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libbasicobjects-0__0.1.1-53.el9.x86_64",
    sha256 = "edd7b31208b80e9f9c94ce54e3f6566cea9b199a3c506387a7ab2a27a3de75da",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libbasicobjects-0.1.1-53.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libblkid-0__2.37.4-15.el9.aarch64",
    sha256 = "212d9990213bc107e7b3030efcb7e90d47cf98dc43605d495509c7ebae8b1957",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libblkid-2.37.4-15.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libblkid-0__2.37.4-15.el9.x86_64",
    sha256 = "a1097a80ec78e6a4beb23940b053fc574f1a45a206ad68eac85681145e2923ae",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libblkid-2.37.4-15.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libbpf-2__1.2.0-1.el9.aarch64",
    sha256 = "58b7650252312edb3a085aec9640fdb940fefeb8847f124ff66e3c5e8b456c25",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libbpf-1.2.0-1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libbpf-2__1.2.0-1.el9.x86_64",
    sha256 = "e604488defe248acd769e738a04949a5e08d64a700917ff01d6a31e4c5819554",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libbpf-1.2.0-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libbrotli-0__1.0.9-6.el9.x86_64",
    sha256 = "a7d211e1059231df8d27fa8f340ac47bdef29b016a49d8a482b13a1f5b4f6c89",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libbrotli-1.0.9-6.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libburn-0__1.5.4-4.el9.aarch64",
    sha256 = "9ee070d18903b22fc0ebd9c94d77f0e8cb2bd344efd9f25e608e6cf2fc1a3af4",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/l/libburn-1.5.4-4.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libburn-0__1.5.4-4.el9.x86_64",
    sha256 = "9e09c60e46163d003b03f397578ebbb0a43d4e372e426df617ff9eb71ea7336c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/l/libburn-1.5.4-4.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libcap-0__2.48-9.el9_2.aarch64",
    sha256 = "e7b8b5ace872eb354539991f9f6cbd5fbd1fd7fcd230893ef81237c09da27f06",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libcap-2.48-9.el9_2.aarch64.rpm",
    ],
)

rpm(
    name = "libcap-0__2.48-9.el9_2.x86_64",
    sha256 = "f399db0064e09ccf71d9a395454fefb1ca38076f18fac9e08104816bd9324c32",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libcap-2.48-9.el9_2.x86_64.rpm",
    ],
)

rpm(
    name = "libcap-ng-0__0.8.2-7.el9.aarch64",
    sha256 = "72cb3896e98585a904913bdeed7ad858faeddd12639969640d1e7616a132cd8b",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libcap-ng-0.8.2-7.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libcap-ng-0__0.8.2-7.el9.x86_64",
    sha256 = "eb8a42e8ac59905dfa2aa1530e4fb7a0b994ff4ae5ee79dd4557f972f1316ae8",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libcap-ng-0.8.2-7.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libcollection-0__0.7.0-53.el9.x86_64",
    sha256 = "f0be13d05591f229b7cdbf0bcd55b43705d3aeb4fe9ca1925a408fa8a34f2361",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libcollection-0.7.0-53.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libcom_err-0__1.46.5-3.el9.aarch64",
    sha256 = "7f462468601c9e26ec920ff4a73d16079e6b551cf500aab4f4c4906b61885b93",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libcom_err-1.46.5-3.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libcom_err-0__1.46.5-3.el9.x86_64",
    sha256 = "26b79a65d0f19b95c949e9bb06bbabbea995e78480a6581deae3cf608dd20d42",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libcom_err-1.46.5-3.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libconfig-0__1.7.2-9.el9.x86_64",
    sha256 = "1ced0126719ae86c4b5360ab303e23eb9dee4dcf68dfc8dc51625de081fd1121",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libconfig-1.7.2-9.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libcurl-minimal-0__7.76.1-26.el9_3.3.aarch64",
    sha256 = "ab56aceed3c189bfdfbaa0843ceb895b1cf56eacb883a57eced056c0ba8434dc",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libcurl-minimal-7.76.1-26.el9_3.3.aarch64.rpm",
    ],
)

rpm(
    name = "libcurl-minimal-0__7.76.1-26.el9_3.3.x86_64",
    sha256 = "c3808b3ff92bdc8ac6be6291b9727f35714ea016c241eca1e18f085aedb03955",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libcurl-minimal-7.76.1-26.el9_3.3.x86_64.rpm",
    ],
)

rpm(
    name = "libdb-0__5.3.28-53.el9.aarch64",
    sha256 = "e0886b0fc3e86a8d8185e626d30875f20db698ffd5749e3060b4872e7bfc6b31",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libdb-5.3.28-53.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libdb-0__5.3.28-53.el9.x86_64",
    sha256 = "4c87bc54f960cf432c39f575a3d77109187e8a07fc1ecf535d719c52c72f87bd",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libdb-5.3.28-53.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libeconf-0__0.4.1-3.el9_2.aarch64",
    sha256 = "372fa7f3fd15dfbe493ce2104966de6ae11bb4b8719b7a133104112a1eab2214",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libeconf-0.4.1-3.el9_2.aarch64.rpm",
    ],
)

rpm(
    name = "libeconf-0__0.4.1-3.el9_2.x86_64",
    sha256 = "c6a90589c000b1a51da97558b1d16a7bc8ad40ea309ca4e57fddf2c50e80edc7",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libeconf-0.4.1-3.el9_2.x86_64.rpm",
    ],
)

rpm(
    name = "libev-0__4.33-5.el9.x86_64",
    sha256 = "fdba7a4e8932746b17b246c9c169eceaf95a36671fcf1580b31c4001ebd16177",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libev-4.33-5.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libevent-0__2.1.12-6.el9.aarch64",
    sha256 = "804e0489c650a64e644931734efe6ec98dcccae5902a1fc2d90fc0e8b64d8e5b",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libevent-2.1.12-6.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libevent-0__2.1.12-6.el9.x86_64",
    sha256 = "4d104f653aa702ba18bc45f5bd4b1f2853b70a8c1cdd64c255570570d20ca91d",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libevent-2.1.12-6.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libfdisk-0__2.37.4-15.el9.aarch64",
    sha256 = "8275883d67bcd98121552b5959ffb033cd7258607d9429e2d56e09d5296ccd0b",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libfdisk-2.37.4-15.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libfdisk-0__2.37.4-15.el9.x86_64",
    sha256 = "f142e06d203fe3de7338c552a7ca98fb50fbf093d78a953ed30524d62201e7c0",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libfdisk-2.37.4-15.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libfdt-0__1.6.0-7.el9.aarch64",
    sha256 = "318ad1b9c8b26501b61b4112a98c877161b42ff1d4bb56b6bf87d04d90f9ff56",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/l/libfdt-1.6.0-7.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libfdt-0__1.6.0-7.el9.x86_64",
    sha256 = "f42aef8f779f79c3fdf5767a93e6949e77af7108e6afcd0da9a3dc8596a67366",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/l/libfdt-1.6.0-7.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libffi-0__3.4.2-8.el9.aarch64",
    sha256 = "1a6fe133eab781288e5ecef0cdde627d57f7d67efb3ded23ec5d9e5a22fb6ab4",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libffi-3.4.2-8.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libffi-0__3.4.2-8.el9.x86_64",
    sha256 = "1bdb4b3b047169bc728c2612b71c31b79bb6f823f50134629bf650dcbf21565a",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libffi-3.4.2-8.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libgcc-0__11.4.1-2.1.el9.aarch64",
    sha256 = "00ecd6bf517f1a30d038be0e9554bbf80e80bc34d75b871fb08ccf6c59bd82d8",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libgcc-11.4.1-2.1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libgcc-0__11.4.1-2.1.el9.x86_64",
    sha256 = "b7b76557bbcdb90b88756a3ab9d1f7e441169d0670c3e7aaeba0b370cfa32e27",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libgcc-11.4.1-2.1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libgcrypt-0__1.10.0-10.el9_2.aarch64",
    sha256 = "cd317ea959dd8dedce41d3f08ed96210b5a0f25287a029565fe4cb0c6ac0419a",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libgcrypt-1.10.0-10.el9_2.aarch64.rpm",
    ],
)

rpm(
    name = "libgcrypt-0__1.10.0-10.el9_2.x86_64",
    sha256 = "edc9b3c4f250cbd1601f0163ea23cbed7a4d8af5e995d4a906122686ddca3cf8",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libgcrypt-1.10.0-10.el9_2.x86_64.rpm",
    ],
)

rpm(
    name = "libgomp-0__11.4.1-2.1.el9.aarch64",
    sha256 = "28d8ca8fe39b0d08dff4c08cd25dbb4fef3b428883743363a102b21a4498ab24",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libgomp-11.4.1-2.1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libgomp-0__11.4.1-2.1.el9.x86_64",
    sha256 = "30162ca942318894a4318db1a568a28ce3366ab0e2111d8c882aaf7f464b0c98",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libgomp-11.4.1-2.1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libgpg-error-0__1.42-5.el9.aarch64",
    sha256 = "e22037efb56a2856af7ee66c0e6a590a5047357e7cfe303abc6a23a53753eb28",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libgpg-error-1.42-5.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libgpg-error-0__1.42-5.el9.x86_64",
    sha256 = "7d48fb4ca1e935a491cb02a85abdd5b91b329168962c1b11ca434c2b80c079fa",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libgpg-error-1.42-5.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libguestfs-1__1.50.1-6.el9.x86_64",
    sha256 = "43be760e56bd157f4b3ecae551837b84cd48d64f25fbf925a6c07a846e2acaad",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/l/libguestfs-1.50.1-6.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libibverbs-0__46.0-1.el9.aarch64",
    sha256 = "52b719b0e9bb87c2651182bc2345c16703f42a361c5a1bf6c20f68d8a787be0b",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libibverbs-46.0-1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libibverbs-0__46.0-1.el9.x86_64",
    sha256 = "877d9bfb11067dc5b4027a8cdc96287a59382c07c04cffcb01aa35fa5a05eaf6",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libibverbs-46.0-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libidn2-0__2.3.0-7.el9.aarch64",
    sha256 = "0832f2067447fb0485ba5220919a926694930006f19e098694e5274d56b6aadc",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libidn2-2.3.0-7.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libidn2-0__2.3.0-7.el9.x86_64",
    sha256 = "be32d8ba7ff8cf790c15d89c5ea18747d7fcc0126782a0e80f15901bb9889b31",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libidn2-2.3.0-7.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libini_config-0__1.3.1-53.el9.x86_64",
    sha256 = "dfced8fe94a782708450c988017e52d2b8b7b69a77d81929cf4d06c913cb4f60",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libini_config-1.3.1-53.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libisoburn-0__1.5.4-4.el9.aarch64",
    sha256 = "38d98ae204a36cb4b1c76d660a2d2432b258730000ee33fb8b87b5bc9d513543",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/l/libisoburn-1.5.4-4.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libisoburn-0__1.5.4-4.el9.x86_64",
    sha256 = "4f9ec7761f21fc7aba9c684e1b8a8bee935fc1c3b0aed21928de898360ce0705",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/l/libisoburn-1.5.4-4.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libisofs-0__1.5.4-4.el9.aarch64",
    sha256 = "022139ad2ace8d0eebac2dffc041de7372290d77f16d7c51e2d65e2ea4555b5f",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/l/libisofs-1.5.4-4.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libisofs-0__1.5.4-4.el9.x86_64",
    sha256 = "725117022cf12d2d090cbaafa47e1402b3f43b699e6ab87ed4e9c890e09dc86d",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/l/libisofs-1.5.4-4.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libksba-0__1.5.1-6.el9_1.x86_64",
    sha256 = "5cd9485fd835a0983a721ec5fa85a17465ded2db2f90b4c8c567a71a2a97861f",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libksba-1.5.1-6.el9_1.x86_64.rpm",
    ],
)

rpm(
    name = "libmnl-0__1.0.4-15.el9.aarch64",
    sha256 = "96714cf501170116bb9d3f56edb8829022b827ba3b16808fdc8af789a66f379a",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libmnl-1.0.4-15.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libmnl-0__1.0.4-15.el9.x86_64",
    sha256 = "6b354c7666726cef879d94bb80b937da271fc0156d993dc3f1a28aae6055e38a",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libmnl-1.0.4-15.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libmount-0__2.37.4-15.el9.aarch64",
    sha256 = "43917409ba273affd23a35abdbd6df3d5aaf757c4b366e60ad420277101bd760",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libmount-2.37.4-15.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libmount-0__2.37.4-15.el9.x86_64",
    sha256 = "ed28d822a671709c442f13083f6f10f1166617bc6bd9d6cf222b65f0125d8cdc",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libmount-2.37.4-15.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libmpc-0__1.2.1-4.el9.aarch64",
    sha256 = "5426e7bb9676b4cab08fe1e0a23a48a8cd49ba883f54b7434245f1a9dd2cd8c6",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/l/libmpc-1.2.1-4.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libmpc-0__1.2.1-4.el9.x86_64",
    sha256 = "c4def74fc686113748590ce9bc8591092947be804650ef56aa161e049660273e",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/l/libmpc-1.2.1-4.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libnetfilter_conntrack-0__1.0.9-1.el9.aarch64",
    sha256 = "8f5469b0207d1ae91b84697c98da3cd62ab4d86e58a1f63bfaad28015bf9992f",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libnetfilter_conntrack-1.0.9-1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libnetfilter_conntrack-0__1.0.9-1.el9.x86_64",
    sha256 = "162fdb1bfe7217bd77f06c19ccf45b274136b434101838ddcafff638fd83cf62",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libnetfilter_conntrack-1.0.9-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libnfnetlink-0__1.0.1-21.el9.aarch64",
    sha256 = "e2b2a93e9cc0ee6e0dd1e699a15766fbec7b2151fb1476c501444988b965ec1b",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libnfnetlink-1.0.1-21.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libnfnetlink-0__1.0.1-21.el9.x86_64",
    sha256 = "06c030f4de5409a9df1df77bd434a3cb25574d36b7b97359e8cc9439f77adca8",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libnfnetlink-1.0.1-21.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libnfsidmap-1__2.5.4-20.el9.x86_64",
    sha256 = "c4af8bfa00cce2a5f0eebb64e39296e81880c31bc4ddfe9439c51d444c549163",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libnfsidmap-2.5.4-20.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libnftnl-0__1.2.2-1.el9.aarch64",
    sha256 = "3e064d1477cf8c696da0dacf435c14769e7fd9f05c4fcfb2192ab4c228041ae6",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libnftnl-1.2.2-1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libnftnl-0__1.2.2-1.el9.x86_64",
    sha256 = "07369f9b69f26a5166bd1ca1af4fef63b77953db3f3556138469129af5f79ffb",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libnftnl-1.2.2-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libnghttp2-0__1.43.0-5.el9_3.1.aarch64",
    sha256 = "7e1f1bab734a2d6f7e01e0d20ac7fddaaf64bb1b8c8beb78d7f78270cb5ccd3c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libnghttp2-1.43.0-5.el9_3.1.aarch64.rpm",
    ],
)

rpm(
    name = "libnghttp2-0__1.43.0-5.el9_3.1.x86_64",
    sha256 = "fff8c687acf6662d48fd267ebad37750e2dd015a821a2c1f8d54a47282ff7462",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libnghttp2-1.43.0-5.el9_3.1.x86_64.rpm",
    ],
)

rpm(
    name = "libnl3-0__3.7.0-1.el9.aarch64",
    sha256 = "91676bf7373a2f665daf7fc28a5d0f9a6feea8926ec773732c0177ea1629094c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libnl3-3.7.0-1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libnl3-0__3.7.0-1.el9.x86_64",
    sha256 = "386a38e80506f462322a0b6f5ad339a3c0919546cf7b73c0d1105ca50d94a994",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libnl3-3.7.0-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libosinfo-0__1.10.0-1.el9.x86_64",
    sha256 = "97e51c58fc9cb62d715781d2067567563e398733ec62ab5b2d7ef60e386d67d0",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/l/libosinfo-1.10.0-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libpath_utils-0__0.2.1-53.el9.x86_64",
    sha256 = "535183c58a000fc1202e43e887b7fc1d7ab664e63723627351d5a805baa177e8",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libpath_utils-0.2.1-53.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libpcap-14__1.10.0-4.el9.aarch64",
    sha256 = "a933a0dbf6a88f1a791569e2fe29215e1b6b454a59e68c265bb86b8a20f9412a",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libpcap-1.10.0-4.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libpcap-14__1.10.0-4.el9.x86_64",
    sha256 = "ae2670f1a65e4b470302a53dde76899123d607555aba7a207e72d1584f2f42b8",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libpcap-1.10.0-4.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libpkgconf-0__1.7.3-10.el9.aarch64",
    sha256 = "646d93ac13091c1399d80942e632af5d1d0bcb29c83ece4968aa3e79b1f36880",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libpkgconf-1.7.3-10.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libpkgconf-0__1.7.3-10.el9.x86_64",
    sha256 = "85df83111841ea9501653408fd86828da263365f8152ac56d92f01940e38519e",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libpkgconf-1.7.3-10.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libpmem-0__1.12.1-1.el9.x86_64",
    sha256 = "7962754be21eb04e0974ad75e199ef8969f03ac20348a0dc3b61d8a59202ac22",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/l/libpmem-1.12.1-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libpng-2__1.6.37-12.el9.aarch64",
    sha256 = "d097557b926ef555cecae507ed55c113a5fae1aa095439cad9c56048c62e7045",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libpng-1.6.37-12.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libpng-2__1.6.37-12.el9.x86_64",
    sha256 = "2fb7ea5028fb07380ec2ece9716763cbe4b456a90574e14ddb93180c8c4bc14f",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libpng-1.6.37-12.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libproxy-0__0.4.15-35.el9.x86_64",
    sha256 = "b5723d56327d929d31efc63d2d746b61a1205269c6dae21d55881bc729a422ec",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libproxy-0.4.15-35.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libpsl-0__0.21.1-5.el9.x86_64",
    sha256 = "30553c652451362ebf346a98ff45fa2417dc25a9a644401b4d86d9000c0346a9",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libpsl-0.21.1-5.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libpwquality-0__1.4.4-8.el9.aarch64",
    sha256 = "dff22028bc366d71fae19c6eecdd277a873cf7f66fa2b24effc16f8733247aa9",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libpwquality-1.4.4-8.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libpwquality-0__1.4.4-8.el9.x86_64",
    sha256 = "d572dfa42d099b58e29fc0c1431c80e1baa4d0555265f79b1a346ebe99ac9ae1",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libpwquality-1.4.4-8.el9.x86_64.rpm",
    ],
)

rpm(
    name = "librdmacm-0__46.0-1.el9.aarch64",
    sha256 = "ccd0b3d3d6ea30b459b58783c13f33ff73189cf98e401d2d293de72ef099b621",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/librdmacm-46.0-1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "librdmacm-0__46.0-1.el9.x86_64",
    sha256 = "91b45c94ea9d12318671d539e08fc3d33dbe372d4d07358f9f3c168e72c59508",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/librdmacm-46.0-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libref_array-0__0.1.5-53.el9.x86_64",
    sha256 = "450cdf91db9553dcf2e929a184719800a22662a2f507acd7cb2cdeeb7a9e4597",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libref_array-0.1.5-53.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libseccomp-0__2.5.2-2.el9.aarch64",
    sha256 = "d3f91fdbe169fe544c24564452f63fe1c6c5fb67bb686146345850223ea1f7ec",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libseccomp-2.5.2-2.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libseccomp-0__2.5.2-2.el9.x86_64",
    sha256 = "c5043228059ffb4e2ef855671909b22bd42784907979a27d25ca9f5163408ad1",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libseccomp-2.5.2-2.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libselinux-0__3.5-1.el9.aarch64",
    sha256 = "f665d48f6cb729a594ffab75235cb4a8c6f36a10f5f906405ae3e8d31db30b4b",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libselinux-3.5-1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libselinux-0__3.5-1.el9.x86_64",
    sha256 = "bcaedf1c0652582fdf9821fc3e39c920a08dc824fd2aac7defef09142e7eadb8",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libselinux-3.5-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libselinux-utils-0__3.5-1.el9.aarch64",
    sha256 = "a563c147edb001fd53932a10f1c1a9353e311c04858e158525c4f3edfa0e9f64",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libselinux-utils-3.5-1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libselinux-utils-0__3.5-1.el9.x86_64",
    sha256 = "5d5a5b1978914cec46cef8c6847af07db6f2a9aaf03b6a2fbce6e8c0da211791",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libselinux-utils-3.5-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libsemanage-0__3.5-2.el9.aarch64",
    sha256 = "00678b02db6c4eaae987ab39c03912f0fd3229489b4f8512dc78973284f6ca92",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libsemanage-3.5-2.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libsemanage-0__3.5-2.el9.x86_64",
    sha256 = "b879526ec63f66e1993203ee04a3097df3d7918446d9e9f77315b7eb4898e66e",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libsemanage-3.5-2.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libsepol-0__3.5-1.el9.aarch64",
    sha256 = "8ce4ea3fe43f6f6a2475da917068ce21e6e10baaa07ecb772e7967b866d33ada",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libsepol-3.5-1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libsepol-0__3.5-1.el9.x86_64",
    sha256 = "ad75fe88f58eac878f9baf690d4c5e30206303f52fae663f0352fe045f877ea1",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libsepol-3.5-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libsigsegv-0__2.13-4.el9.aarch64",
    sha256 = "1935c944375f3bf40913bbda2cd87bbaf25a475be51c1662c24f54eb04da584b",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libsigsegv-2.13-4.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libsigsegv-0__2.13-4.el9.x86_64",
    sha256 = "a80701bd3f67994493b1a14e043d9212032c86fd24374c309cf2b7006900f4da",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libsigsegv-2.13-4.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libslirp-0__4.4.0-7.el9.aarch64",
    sha256 = "57a957b06533ee8b482a371a492e9a6ebf3ec84995c43965bd61af45a565444b",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/l/libslirp-4.4.0-7.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libslirp-0__4.4.0-7.el9.x86_64",
    sha256 = "9e139bea16fc979b10db9af8c6f29cd205f50450d09db2a1dd6744512193a4ae",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/l/libslirp-4.4.0-7.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libsmartcols-0__2.37.4-15.el9.aarch64",
    sha256 = "7aeaa93f31c347498925d6a79e78711a929c7acdc7970ab13f4326073e88fdfa",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libsmartcols-2.37.4-15.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libsmartcols-0__2.37.4-15.el9.x86_64",
    sha256 = "e7dab24297f6642c7e5c27db1d9291f3af1a9f808e78640ec93f19ee72c51d6b",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libsmartcols-2.37.4-15.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libsoup-0__2.72.0-8.el9.x86_64",
    sha256 = "29de6bc5022554f6554629c453fd8f021248c5a134a2147310c8facb967caef1",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/l/libsoup-2.72.0-8.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libss-0__1.46.5-3.el9.aarch64",
    sha256 = "f38b25511022cef1e2cbde696f6e9f7c27c66690aec552ad6dbb7419a1e1f026",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libss-1.46.5-3.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libss-0__1.46.5-3.el9.x86_64",
    sha256 = "320735da9ce042a9d97783664191ec807c988a1f91d26a03557aa00fc3f13a75",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libss-1.46.5-3.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libssh-0__0.10.4-12.el9_3.aarch64",
    sha256 = "d26f71897358719e2f62689a91275315998f03e29409cd8b8d87877dfe182cff",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libssh-0.10.4-12.el9_3.aarch64.rpm",
    ],
)

rpm(
    name = "libssh-0__0.10.4-12.el9_3.x86_64",
    sha256 = "0c1cd56f961ee07dad9fda1e9663035226adc8fe943897d12128532c02657422",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libssh-0.10.4-12.el9_3.x86_64.rpm",
    ],
)

rpm(
    name = "libssh-config-0__0.10.4-12.el9_3.aarch64",
    sha256 = "4dec2af581df1c124229c102e7c78d3ea057378db770df9a00f6973777443b33",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libssh-config-0.10.4-12.el9_3.noarch.rpm",
    ],
)

rpm(
    name = "libssh-config-0__0.10.4-12.el9_3.x86_64",
    sha256 = "4dec2af581df1c124229c102e7c78d3ea057378db770df9a00f6973777443b33",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libssh-config-0.10.4-12.el9_3.noarch.rpm",
    ],
)

rpm(
    name = "libsss_idmap-0__2.9.1-4.el9_3.5.aarch64",
    sha256 = "7beeda62ae11e676d5571f9c97db481c90ff142c0c79e9567cbea111c846025c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libsss_idmap-2.9.1-4.el9_3.5.aarch64.rpm",
    ],
)

rpm(
    name = "libsss_idmap-0__2.9.1-4.el9_3.5.x86_64",
    sha256 = "d380d188720fd424e823ebf78508bf2a2fc8ae5f5a054661f6097464d7340aae",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libsss_idmap-2.9.1-4.el9_3.5.x86_64.rpm",
    ],
)

rpm(
    name = "libsss_nss_idmap-0__2.9.1-4.el9_3.5.aarch64",
    sha256 = "003a09c1c502c82cedb4a6537f0b42c6e3ce4b0816f481b17d6cc3509bbbd91b",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libsss_nss_idmap-2.9.1-4.el9_3.5.aarch64.rpm",
    ],
)

rpm(
    name = "libsss_nss_idmap-0__2.9.1-4.el9_3.5.x86_64",
    sha256 = "6f6519f1540fb3cfe68000d34b4934f9dd73676bd0ad06604b6d375342112449",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libsss_nss_idmap-2.9.1-4.el9_3.5.x86_64.rpm",
    ],
)

rpm(
    name = "libstdc__plus____plus__-0__11.4.1-2.1.el9.aarch64",
    sha256 = "fd1a1bd9bfcdaac18b6201e253966c1752c73655ea5d21f17e9e927d59cab02c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libstdc++-11.4.1-2.1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libstdc__plus____plus__-0__11.4.1-2.1.el9.x86_64",
    sha256 = "1e0d56f2c0ae5c5ac24ad61f8f78ec209cc09b4555f9763d0bde6da9d0a48b7b",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libstdc++-11.4.1-2.1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libtasn1-0__4.16.0-8.el9_1.aarch64",
    sha256 = "3963d58e43412e91e47454836e5431fbc77014d411ac6eec4847fc7cede46a6d",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libtasn1-4.16.0-8.el9_1.aarch64.rpm",
    ],
)

rpm(
    name = "libtasn1-0__4.16.0-8.el9_1.x86_64",
    sha256 = "f62a78a4d12241611733a45d896511c9825d06116373f4277e08acbae7565322",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libtasn1-4.16.0-8.el9_1.x86_64.rpm",
    ],
)

rpm(
    name = "libtirpc-0__1.3.3-2.el9.aarch64",
    sha256 = "f3745a230155bdd51ce7be76f7c457eda1c2caca73600703a841e7fee156fde9",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libtirpc-1.3.3-2.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libtirpc-0__1.3.3-2.el9.x86_64",
    sha256 = "7f638eef13d99b9985ca6019495fa86b530896ec76f790462c82ed347bece07b",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libtirpc-1.3.3-2.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libtpms-0__0.9.1-3.20211126git1ff6fe1f43.el9_2.aarch64",
    sha256 = "34ff72ddf8b831708702a0fea060f003203f1391878a84bf92c0a5906de71e83",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/l/libtpms-0.9.1-3.20211126git1ff6fe1f43.el9_2.aarch64.rpm",
    ],
)

rpm(
    name = "libtpms-0__0.9.1-3.20211126git1ff6fe1f43.el9_2.x86_64",
    sha256 = "272958e38060dc9d10d7ba16dd3772467478700a4f78bb2680d55c087e900003",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/l/libtpms-0.9.1-3.20211126git1ff6fe1f43.el9_2.x86_64.rpm",
    ],
)

rpm(
    name = "libubsan-0__11.4.1-2.1.el9.aarch64",
    sha256 = "314f350e43db98e97cc5739d32641a272c8e07bcb1a78505505f25fa6d131a8b",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/l/libubsan-11.4.1-2.1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libunistring-0__0.9.10-15.el9.aarch64",
    sha256 = "640263402602c1f5a77a2ecde6b73cfd71e6bb574619f6ead58fdf61c0f4f63e",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libunistring-0.9.10-15.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libunistring-0__0.9.10-15.el9.x86_64",
    sha256 = "7e8b90a282ec310de6766619056296bdf666f3040f22cff211cd52710b39ece5",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libunistring-0.9.10-15.el9.x86_64.rpm",
    ],
)

rpm(
    name = "liburing-0__2.3-2.el9.aarch64",
    sha256 = "199ba4def77eb812156657073a09a58b272a214b710fc8915810d1184f3d38d2",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/l/liburing-2.3-2.el9.aarch64.rpm",
    ],
)

rpm(
    name = "liburing-0__2.3-2.el9.x86_64",
    sha256 = "dcf645688c592b419d622b071a5eaf52d3519249c9e60cd6acafcd91a696b343",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/l/liburing-2.3-2.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libusbx-0__1.0.26-1.el9.aarch64",
    sha256 = "eb01bae3ea719c9f2dea8b135cc4831fdbec43add0dfc1983edf4cb2a3feb178",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libusbx-1.0.26-1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libusbx-0__1.0.26-1.el9.x86_64",
    sha256 = "efb7bf9c0660d748c2813bf9a37a89de988536888bfe6d7d71fc27dbccb8ee27",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libusbx-1.0.26-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libutempter-0__1.2.1-6.el9.aarch64",
    sha256 = "628e1aa68e0dbb62cbb87478bcd0b03737d703a199edbd9c7067515722951f65",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libutempter-1.2.1-6.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libutempter-0__1.2.1-6.el9.x86_64",
    sha256 = "146dca82c8f1df8135ae7d5cc4aa4af35e02e60f1f61143badc9c5f7ff5029b9",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libutempter-1.2.1-6.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libuuid-0__2.37.4-15.el9.aarch64",
    sha256 = "2f7887b1a801f8ef13da9a862c0a8e324511ed4502f793903848d1e945138989",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libuuid-2.37.4-15.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libuuid-0__2.37.4-15.el9.x86_64",
    sha256 = "bf8238ff0dc198fe9bcd60a087f03adbeb5271d4fe62d60dfdfa35d106e91e1e",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libuuid-2.37.4-15.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libverto-0__0.3.2-3.el9.aarch64",
    sha256 = "d12d7f526c5ef9957f6e1d9be4b2b77ff892040e08112f0a8804677e3c668b64",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libverto-0.3.2-3.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libverto-0__0.3.2-3.el9.x86_64",
    sha256 = "f430f1b95b7467c461c7a745eba07beab00306984f2f21ecfcc04f37100405d1",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libverto-0.3.2-3.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libverto-libev-0__0.3.2-3.el9.x86_64",
    sha256 = "a7394271ca60122619fb7d1693f2a318d9e5bea92352897d145c78d190bf0ee5",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libverto-libev-0.3.2-3.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libvirt-client-0__9.5.0-7.el9_3.aarch64",
    sha256 = "587cb37b6dacf4352c42b1e1b7c76a94c367e4bf9bf35f9193c67b8c50cd09c9",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/l/libvirt-client-9.5.0-7.el9_3.aarch64.rpm",
    ],
)

rpm(
    name = "libvirt-client-0__9.5.0-7.el9_3.x86_64",
    sha256 = "309bcb743c33a3dfe4611a6bc63ec93f9031b5289c073d6e7f556ca9c2d942d3",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/l/libvirt-client-9.5.0-7.el9_3.x86_64.rpm",
    ],
)

rpm(
    name = "libvirt-daemon-common-0__9.5.0-7.el9_3.aarch64",
    sha256 = "81ff37e98ad91e70965e6025832a5ee869a13c709d6c22ec1fc26b8f389ecde7",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/l/libvirt-daemon-common-9.5.0-7.el9_3.aarch64.rpm",
    ],
)

rpm(
    name = "libvirt-daemon-common-0__9.5.0-7.el9_3.x86_64",
    sha256 = "92493ae7d84b46fabf748f7317976131abd7b6ae7d3c3a017cd237131e2aeaea",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/l/libvirt-daemon-common-9.5.0-7.el9_3.x86_64.rpm",
    ],
)

rpm(
    name = "libvirt-daemon-driver-qemu-0__9.5.0-7.el9_3.aarch64",
    sha256 = "043681d841653d1efe7f6784a328f2fcf605a07b0bd51612fec49fcdd215f847",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/l/libvirt-daemon-driver-qemu-9.5.0-7.el9_3.aarch64.rpm",
    ],
)

rpm(
    name = "libvirt-daemon-driver-qemu-0__9.5.0-7.el9_3.x86_64",
    sha256 = "b79b8828101f3d33996df83a9c273aab2fe13b2e19a5c4439ce111e53be01624",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/l/libvirt-daemon-driver-qemu-9.5.0-7.el9_3.x86_64.rpm",
    ],
)

rpm(
    name = "libvirt-daemon-driver-secret-0__9.5.0-7.el9_3.x86_64",
    sha256 = "9798514ab56d6175495c4fcb09f84cde74c032c0589d4e9383f3bbe5efadd688",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/l/libvirt-daemon-driver-secret-9.5.0-7.el9_3.x86_64.rpm",
    ],
)

rpm(
    name = "libvirt-daemon-driver-storage-core-0__9.5.0-7.el9_3.x86_64",
    sha256 = "e99c8f4668ecea0e596487cb05ca98c970657758bf30184c8bac4dad684ecb2e",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/l/libvirt-daemon-driver-storage-core-9.5.0-7.el9_3.x86_64.rpm",
    ],
)

rpm(
    name = "libvirt-daemon-log-0__9.5.0-7.el9_3.aarch64",
    sha256 = "db0aa21fcb035879044ef2b412125965ab4630db9e552ada106a93b578dc9429",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/l/libvirt-daemon-log-9.5.0-7.el9_3.aarch64.rpm",
    ],
)

rpm(
    name = "libvirt-daemon-log-0__9.5.0-7.el9_3.x86_64",
    sha256 = "393ce1ac03b07a8e752994efbd0967e7159bb0201547cb9852b291476cd91d70",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/l/libvirt-daemon-log-9.5.0-7.el9_3.x86_64.rpm",
    ],
)

rpm(
    name = "libvirt-devel-0__9.5.0-7.el9_3.aarch64",
    sha256 = "b8e9045d891eb9f4040876cda843c615a8940681a03aa8e4bd77fad5503b6a0f",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/CRB/aarch64/os/Packages/l/libvirt-devel-9.5.0-7.el9_3.aarch64.rpm",
    ],
)

rpm(
    name = "libvirt-devel-0__9.5.0-7.el9_3.x86_64",
    sha256 = "f6b32f7a201bba4d57c17e95c8415ad6d8280437eb9e05b970307d7f7036f67b",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/CRB/x86_64/os/Packages/l/libvirt-devel-9.5.0-7.el9_3.x86_64.rpm",
    ],
)

rpm(
    name = "libvirt-libs-0__9.5.0-7.el9_3.aarch64",
    sha256 = "e613bcb822098bbfe7637d52c227e00130e0275d0ab131762a6ae1607ff482e8",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/l/libvirt-libs-9.5.0-7.el9_3.aarch64.rpm",
    ],
)

rpm(
    name = "libvirt-libs-0__9.5.0-7.el9_3.x86_64",
    sha256 = "4e0ae3f1e75e43dcc0460fe527e5f3361ea1d0787c6e9e4c8f143aceef8e8efc",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/l/libvirt-libs-9.5.0-7.el9_3.x86_64.rpm",
    ],
)

rpm(
    name = "libxcrypt-0__4.4.18-3.el9.aarch64",
    sha256 = "ec12e0266ce1f96af43495c95f95fbb6d972af576f19473ea231985f8cd4d2d6",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libxcrypt-4.4.18-3.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libxcrypt-0__4.4.18-3.el9.x86_64",
    sha256 = "e3c178ed2e04ac25699d5af612fad51694a23f5d544b72cab2f65d35b8db5f28",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libxcrypt-4.4.18-3.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libxcrypt-devel-0__4.4.18-3.el9.aarch64",
    sha256 = "efde6bb81af1da9757208a7212c1db913315622249a1eb4f98ff34f1090c329d",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/l/libxcrypt-devel-4.4.18-3.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libxcrypt-devel-0__4.4.18-3.el9.x86_64",
    sha256 = "f98951be16cb84133ac14201348a202c9884f8958f908b6040fb5db12e4dba81",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/l/libxcrypt-devel-4.4.18-3.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libxcrypt-static-0__4.4.18-3.el9.aarch64",
    sha256 = "c1790a96e11c0765290f824166edfb77dd9fc2c973cb874b0afac8fd1314b574",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/CRB/aarch64/os/Packages/l/libxcrypt-static-4.4.18-3.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libxcrypt-static-0__4.4.18-3.el9.x86_64",
    sha256 = "d619736aa4ce6a1787a900071f6d1486a6c3e3985b9ecda7621cc4ad0ace17e3",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/CRB/x86_64/os/Packages/l/libxcrypt-static-4.4.18-3.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libxml2-0__2.9.13-5.el9_3.aarch64",
    sha256 = "56cfd234163b771068ae96d37e1b0e1c648471ae097eb37f6de6c3c38b0ede04",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libxml2-2.9.13-5.el9_3.aarch64.rpm",
    ],
)

rpm(
    name = "libxml2-0__2.9.13-5.el9_3.x86_64",
    sha256 = "b28cb915e66606b984bc0b583ef43bf9205541d3bf6ddddefc694d357581e5ee",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libxml2-2.9.13-5.el9_3.x86_64.rpm",
    ],
)

rpm(
    name = "libxslt-0__1.1.34-9.el9.x86_64",
    sha256 = "0127ecfbfb6b1f3bafccb4057e882b9f5f39123fdb55d33e64a5f0fb943810d6",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/l/libxslt-1.1.34-9.el9.x86_64.rpm",
    ],
)

rpm(
    name = "libzstd-0__1.5.1-2.el9.aarch64",
    sha256 = "b997fa077e854b7541c044dd2c213e9ecf18b67176a9e7f70dba11dc53f48d5e",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/libzstd-1.5.1-2.el9.aarch64.rpm",
    ],
)

rpm(
    name = "libzstd-0__1.5.1-2.el9.x86_64",
    sha256 = "517b3080de2e0891cc346ba6b1548ef438b95dbede0e6e7a6deae89fc241f5bc",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/libzstd-1.5.1-2.el9.x86_64.rpm",
    ],
)

rpm(
    name = "lua-libs-0__5.4.4-4.el9.aarch64",
    sha256 = "77ed02fb0f50b6f4cdfd409304e4cc5016dccc50cbb1e6e4c663c0498a5219b6",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/lua-libs-5.4.4-4.el9.aarch64.rpm",
    ],
)

rpm(
    name = "lua-libs-0__5.4.4-4.el9.x86_64",
    sha256 = "164f78bdc4b37210c54752761d48a229c935824503d5c591c020e447318a1749",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/lua-libs-5.4.4-4.el9.x86_64.rpm",
    ],
)

rpm(
    name = "lz4-libs-0__1.9.3-5.el9.aarch64",
    sha256 = "8640e8b3ba387e5ec9036e89903add891d7c960bbf0378797746cb43e0e2208f",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/lz4-libs-1.9.3-5.el9.aarch64.rpm",
    ],
)

rpm(
    name = "lz4-libs-0__1.9.3-5.el9.x86_64",
    sha256 = "60f82f4c3f76a543ab247acb37cb439d9de9e40c410ac2f315d6805717d6283e",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/lz4-libs-1.9.3-5.el9.x86_64.rpm",
    ],
)

rpm(
    name = "lzo-0__2.10-7.el9.aarch64",
    sha256 = "ce71bce707d6f763dc41b4f21ac5aabbdfc80ae7c29a6bf116adffc27f2a83a2",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/lzo-2.10-7.el9.aarch64.rpm",
    ],
)

rpm(
    name = "lzo-0__2.10-7.el9.x86_64",
    sha256 = "e204370ce22c35f18d784ad404c2892e2ffe946d5e0378c8d1044f6554fbe860",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/lzo-2.10-7.el9.x86_64.rpm",
    ],
)

rpm(
    name = "lzop-0__1.04-8.el9.aarch64",
    sha256 = "658d9b0c6baa892802f0f21966ba381d8311fab278e46c5e2983b49ae6870201",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/l/lzop-1.04-8.el9.aarch64.rpm",
    ],
)

rpm(
    name = "lzop-0__1.04-8.el9.x86_64",
    sha256 = "3db4bc7fb57b4ed0c4a75f2104b49a60e25c4c502a15636754a3d1811484e265",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/l/lzop-1.04-8.el9.x86_64.rpm",
    ],
)

rpm(
    name = "make-1__4.3-7.el9.aarch64",
    sha256 = "fa4cdcbbecef3122c8170db6b0702ffd8a6f13eee9f4307f103c1c1e0abc5153",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/m/make-4.3-7.el9.aarch64.rpm",
    ],
)

rpm(
    name = "make-1__4.3-7.el9.x86_64",
    sha256 = "c1e403a726da86aeae4920c50ed7356c393b28447acae854d74a022a64d0fec3",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/m/make-4.3-7.el9.x86_64.rpm",
    ],
)

rpm(
    name = "mpfr-0__4.1.0-7.el9.aarch64",
    sha256 = "41ce16a26c839c36cd84a836361ecd3ca4bc966bddc945af8cb70886331511ee",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/m/mpfr-4.1.0-7.el9.aarch64.rpm",
    ],
)

rpm(
    name = "mpfr-0__4.1.0-7.el9.x86_64",
    sha256 = "88e46af29bde609d8f414313d0090e30501cc38ddf5c6a1bffe34ae896ca936e",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/m/mpfr-4.1.0-7.el9.x86_64.rpm",
    ],
)

rpm(
    name = "ncurses-base-0__6.2-10.20210508.el9.aarch64",
    sha256 = "88a506c88f2964c71d7eafbef76f57870d799c041560bd929608c5853e632d98",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/n/ncurses-base-6.2-10.20210508.el9.noarch.rpm",
    ],
)

rpm(
    name = "ncurses-base-0__6.2-10.20210508.el9.x86_64",
    sha256 = "88a506c88f2964c71d7eafbef76f57870d799c041560bd929608c5853e632d98",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/n/ncurses-base-6.2-10.20210508.el9.noarch.rpm",
    ],
)

rpm(
    name = "ncurses-libs-0__6.2-10.20210508.el9.aarch64",
    sha256 = "4a4dfaff385ec7d1bcef1a0d1ef644d5a08ac844dd333594170b460c9f5b9ffb",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/n/ncurses-libs-6.2-10.20210508.el9.aarch64.rpm",
    ],
)

rpm(
    name = "ncurses-libs-0__6.2-10.20210508.el9.x86_64",
    sha256 = "ea2d4bd41eb314ea7537dc47d6952091700a5ba82f44ac98b767d5ac3efa94f6",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/n/ncurses-libs-6.2-10.20210508.el9.x86_64.rpm",
    ],
)

rpm(
    name = "ndctl-libs-0__71.1-8.el9.x86_64",
    sha256 = "d2faa74fdf22dcef61289a672d09127edcc59ec368211d161fa715821a630632",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/n/ndctl-libs-71.1-8.el9.x86_64.rpm",
    ],
)

rpm(
    name = "nettle-0__3.8-3.el9_0.aarch64",
    sha256 = "3dd74bc4cff017a46500656e9552c54b005c345dde1aa8e3cbb8447cfe88e7e1",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/n/nettle-3.8-3.el9_0.aarch64.rpm",
    ],
)

rpm(
    name = "nettle-0__3.8-3.el9_0.x86_64",
    sha256 = "8b26d9abcaeadde048555c7187753b64172be4cca206f704ddf2319772bc4beb",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/n/nettle-3.8-3.el9_0.x86_64.rpm",
    ],
)

rpm(
    name = "nfs-utils-1__2.5.4-20.el9.x86_64",
    sha256 = "fcae10e1db0afc9b8d5014357d49a7b818bc481efb789872b89630a7ed42c740",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/n/nfs-utils-2.5.4-20.el9.x86_64.rpm",
    ],
)

rpm(
    name = "nftables-1__1.0.4-11.el9_3.aarch64",
    sha256 = "7bed4ba04f441103027fe8ac731d8b31eddfc90d4939073d317c760dc0ced72e",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/n/nftables-1.0.4-11.el9_3.aarch64.rpm",
    ],
)

rpm(
    name = "nftables-1__1.0.4-11.el9_3.x86_64",
    sha256 = "8f1630bf62cb80a49c88b6a4bcafacbc902c3cf623166e13199ccfa7e8369489",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/n/nftables-1.0.4-11.el9_3.x86_64.rpm",
    ],
)

rpm(
    name = "nmap-ncat-3__7.92-1.el9.aarch64",
    sha256 = "9c789dce2491e075b359bc08b46c435627b0fe62ed2aed9a2754dcd08bc086e0",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/n/nmap-ncat-7.92-1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "nmap-ncat-3__7.92-1.el9.x86_64",
    sha256 = "667d49f4f2b1e1dc9f8b178c10dc79a6661bf9c989d320c7344e9387c8d8ab7f",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/n/nmap-ncat-7.92-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "npth-0__1.6-8.el9.x86_64",
    sha256 = "a96a4af76f58645fe34c526c684a45a5a97642c1836bfb3a91ef29520cb21324",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/n/npth-1.6-8.el9.x86_64.rpm",
    ],
)

rpm(
    name = "numactl-libs-0__2.0.16-1.el9.aarch64",
    sha256 = "70294a9add5cc84a99a15258261ee3f06244a416e501d92d07c89ddac747b192",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/n/numactl-libs-2.0.16-1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "numactl-libs-0__2.0.16-1.el9.x86_64",
    sha256 = "1386704a453b2f883e2658621d16654740a09d697647fef07c0aa6a8530d1557",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/n/numactl-libs-2.0.16-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "numad-0__0.5-36.20150602git.el9.aarch64",
    sha256 = "72ab4c1f1300ef9df3f7cef76f10f716a9e12a47ac7a3b2a09bd18e7bc70bd04",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/n/numad-0.5-36.20150602git.el9.aarch64.rpm",
    ],
)

rpm(
    name = "numad-0__0.5-36.20150602git.el9.x86_64",
    sha256 = "26d5176357e73e7c8d7e5065c3a76759552a09f1f8632cb2d2b7ee47ff65ff22",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/n/numad-0.5-36.20150602git.el9.x86_64.rpm",
    ],
)

rpm(
    name = "openldap-0__2.6.3-1.el9.aarch64",
    sha256 = "5ae57ff07056352afe0a35a3acd629a6067dda3d327696ae1d362b091ac6945c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/o/openldap-2.6.3-1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "openldap-0__2.6.3-1.el9.x86_64",
    sha256 = "3dff4c7d167948e7879ebc87eeb75c278191fdaf6c1747a7a09b38a3da4e231f",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/o/openldap-2.6.3-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "openssl-1__3.0.7-25.el9_3.aarch64",
    sha256 = "9c049321ba57f85826c1cccf48b500a9919843ab362fe3124a7f3aac5bcde909",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/o/openssl-3.0.7-25.el9_3.aarch64.rpm",
    ],
)

rpm(
    name = "openssl-1__3.0.7-25.el9_3.x86_64",
    sha256 = "27be21eee1243192d544a785557601d5d256a851338286c6c28ff583cf4db718",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/o/openssl-3.0.7-25.el9_3.x86_64.rpm",
    ],
)

rpm(
    name = "openssl-libs-1__3.0.7-25.el9_3.aarch64",
    sha256 = "54e78409218cda5c47abd5bd62c6e4549ec1b3f52cd3145fd13ebd55ee1f2a84",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/o/openssl-libs-3.0.7-25.el9_3.aarch64.rpm",
    ],
)

rpm(
    name = "openssl-libs-1__3.0.7-25.el9_3.x86_64",
    sha256 = "166eb36e368701bbd734fa35c866e0a94b24a780311737bfe2cff40ff5e1a15c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/o/openssl-libs-3.0.7-25.el9_3.x86_64.rpm",
    ],
)

rpm(
    name = "osinfo-db-0__20230518-1.el9.x86_64",
    sha256 = "402c5e2d1ca029665bf9eab43f24bfcc3d4a4b56435b2c652df15787345516be",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/o/osinfo-db-20230518-1.el9.noarch.rpm",
    ],
)

rpm(
    name = "osinfo-db-tools-0__1.10.0-1.el9.x86_64",
    sha256 = "6a55be53ab583dc5a14021e4e799f77d0714d8401e53c36bacb61cb415350a01",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/o/osinfo-db-tools-1.10.0-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "p11-kit-0__0.24.1-2.el9.aarch64",
    sha256 = "2115edc84ecf17aafd73ee1e61e55030ce77a2f5aee0a8cfd2c7f53612df3a20",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/p/p11-kit-0.24.1-2.el9.aarch64.rpm",
    ],
)

rpm(
    name = "p11-kit-0__0.24.1-2.el9.x86_64",
    sha256 = "2e9ba88f7638b89033dd8e3559f9c5c0a84cfa40110d061131391283eff07017",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/p11-kit-0.24.1-2.el9.x86_64.rpm",
    ],
)

rpm(
    name = "p11-kit-trust-0__0.24.1-2.el9.aarch64",
    sha256 = "f4a15510e60f410597da7e2bbc0cc1966cee9c3192f9f78310891d229b614659",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/p/p11-kit-trust-0.24.1-2.el9.aarch64.rpm",
    ],
)

rpm(
    name = "p11-kit-trust-0__0.24.1-2.el9.x86_64",
    sha256 = "f3323fd8f94b5590ce6b8a191db48315eee46e1f4c5b1902b1c0b14982dc4b34",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/p11-kit-trust-0.24.1-2.el9.x86_64.rpm",
    ],
)

rpm(
    name = "pam-0__1.5.1-15.el9.aarch64",
    sha256 = "e74b65dc25a73405dc94381f20876bfb39867d8d0077b0c62a9e983f2ef4c604",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/p/pam-1.5.1-15.el9.aarch64.rpm",
    ],
)

rpm(
    name = "pam-0__1.5.1-15.el9.x86_64",
    sha256 = "78e92745d3a8fed7b4c61ab9665278d5247dd2402982bd7a3456466dd1014557",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/pam-1.5.1-15.el9.x86_64.rpm",
    ],
)

rpm(
    name = "parted-0__3.5-2.el9.x86_64",
    sha256 = "dfb1ce7a70255119b4919a7b61112bfd7661a90f1063b0c77346e64a4eebc973",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/parted-3.5-2.el9.x86_64.rpm",
    ],
)

rpm(
    name = "passt-0__0__caret__20230818.g0af928e-4.el9.aarch64",
    sha256 = "8c1d043ec433646efc0135da2bf1ca4f02673a2af172a46bee43e8e5c44a10e5",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/p/passt-0%5E20230818.g0af928e-4.el9.aarch64.rpm",
    ],
)

rpm(
    name = "passt-0__0__caret__20230818.g0af928e-4.el9.x86_64",
    sha256 = "52c45a59fdd95c16532fe5c2196478b920d78a342391eecc832c2c2cccd1a473",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/p/passt-0%5E20230818.g0af928e-4.el9.x86_64.rpm",
    ],
)

rpm(
    name = "pcre-0__8.44-3.el9.3.aarch64",
    sha256 = "2e799d49788c8ab4ce81a564e50308f60cc8e3bad86b4fd0f0cc628d4dc900f0",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/p/pcre-8.44-3.el9.3.aarch64.rpm",
    ],
)

rpm(
    name = "pcre-0__8.44-3.el9.3.x86_64",
    sha256 = "167b0160dfe4bda726ed0f47e3773d6d4ee73dc032f5c09e768ffd4ac5681d71",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/pcre-8.44-3.el9.3.x86_64.rpm",
    ],
)

rpm(
    name = "pcre2-0__10.40-2.el9.aarch64",
    sha256 = "ac166b2214e5e427722c2f4c24befe4c05c5593866e84045c46721334f47e86f",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/p/pcre2-10.40-2.el9.aarch64.rpm",
    ],
)

rpm(
    name = "pcre2-0__10.40-2.el9.x86_64",
    sha256 = "9c309aff834d55fffcb84b175032869d2d93656ec6a78df2b7cf7dd44319c1aa",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/pcre2-10.40-2.el9.x86_64.rpm",
    ],
)

rpm(
    name = "pcre2-syntax-0__10.40-2.el9.aarch64",
    sha256 = "b121946dd77d3aa907935fd04730c8447758fb96102c332652815eea129246f3",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/p/pcre2-syntax-10.40-2.el9.noarch.rpm",
    ],
)

rpm(
    name = "pcre2-syntax-0__10.40-2.el9.x86_64",
    sha256 = "b121946dd77d3aa907935fd04730c8447758fb96102c332652815eea129246f3",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/pcre2-syntax-10.40-2.el9.noarch.rpm",
    ],
)

rpm(
    name = "pixman-0__0.40.0-6.el9_3.aarch64",
    sha256 = "25c78517864ddb7189abb5ce1771cd8e4bdaa2db0ecd78d36051ad361db563de",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/p/pixman-0.40.0-6.el9_3.aarch64.rpm",
    ],
)

rpm(
    name = "pixman-0__0.40.0-6.el9_3.x86_64",
    sha256 = "f90f7b61c355aae65c1c94ab19a6538212ba4f64236457fee42793710331321c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/p/pixman-0.40.0-6.el9_3.x86_64.rpm",
    ],
)

rpm(
    name = "pkgconf-0__1.7.3-10.el9.aarch64",
    sha256 = "7b7d43f3c29ab0f7eb10ca100e1b8c95713f943a48d9168261f2170601b0be91",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/p/pkgconf-1.7.3-10.el9.aarch64.rpm",
    ],
)

rpm(
    name = "pkgconf-0__1.7.3-10.el9.x86_64",
    sha256 = "6a5ee8580ea3fb5edf1722c7a3941c1a5a431040a251dbff0e34f85c8352c93a",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/pkgconf-1.7.3-10.el9.x86_64.rpm",
    ],
)

rpm(
    name = "pkgconf-m4-0__1.7.3-10.el9.aarch64",
    sha256 = "ac0ab185f11a413f08f645b6225aa67f4542b23e293cbc7af78d71e0259d7389",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/p/pkgconf-m4-1.7.3-10.el9.noarch.rpm",
    ],
)

rpm(
    name = "pkgconf-m4-0__1.7.3-10.el9.x86_64",
    sha256 = "ac0ab185f11a413f08f645b6225aa67f4542b23e293cbc7af78d71e0259d7389",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/pkgconf-m4-1.7.3-10.el9.noarch.rpm",
    ],
)

rpm(
    name = "pkgconf-pkg-config-0__1.7.3-10.el9.aarch64",
    sha256 = "f41b0b4d0f9ce0a9e63edcd9c141587b7db020e2e69917cdccfe32df9db21aa3",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/p/pkgconf-pkg-config-1.7.3-10.el9.aarch64.rpm",
    ],
)

rpm(
    name = "pkgconf-pkg-config-0__1.7.3-10.el9.x86_64",
    sha256 = "c7e4569fe2d676e76dc689a751884541bcd6595616e8c9fb00bc198bce642031",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/pkgconf-pkg-config-1.7.3-10.el9.x86_64.rpm",
    ],
)

rpm(
    name = "policycoreutils-0__3.5-3.el9_3.aarch64",
    sha256 = "de29c8e92c673fdc86d896da063e2369db852f804589ef6feea805601d03abca",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/p/policycoreutils-3.5-3.el9_3.aarch64.rpm",
    ],
)

rpm(
    name = "policycoreutils-0__3.5-3.el9_3.x86_64",
    sha256 = "186f2d2f4c2214b9edf9eb6da3cafde60e7bebd02c088a8af56a408688b07d03",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/policycoreutils-3.5-3.el9_3.x86_64.rpm",
    ],
)

rpm(
    name = "polkit-0__0.117-11.el9.aarch64",
    sha256 = "8af109986b4bde01ce87e4b272b07e13dba9f6fa6c545e40741111d979eb4548",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/p/polkit-0.117-11.el9.aarch64.rpm",
    ],
)

rpm(
    name = "polkit-0__0.117-11.el9.x86_64",
    sha256 = "bd58ba1412ea75be83259e8d6437710d1a1dc253a4b2b965dcad4c074cefeab9",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/polkit-0.117-11.el9.x86_64.rpm",
    ],
)

rpm(
    name = "polkit-libs-0__0.117-11.el9.aarch64",
    sha256 = "9b7728119c318a68143463c5cc46a9d175692cb373e7f151e472775a22467814",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/p/polkit-libs-0.117-11.el9.aarch64.rpm",
    ],
)

rpm(
    name = "polkit-libs-0__0.117-11.el9.x86_64",
    sha256 = "cc5ef7386278ee3d6bffea06ec92e8c26b00b9d16b339a947fe3c7c02a30ab2b",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/polkit-libs-0.117-11.el9.x86_64.rpm",
    ],
)

rpm(
    name = "polkit-pkla-compat-0__0.1-21.el9.aarch64",
    sha256 = "da32d58f42367d8070211e4077a616f8e392ba17874f6b84c6cba6bed6addbec",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/p/polkit-pkla-compat-0.1-21.el9.aarch64.rpm",
    ],
)

rpm(
    name = "polkit-pkla-compat-0__0.1-21.el9.x86_64",
    sha256 = "1dc0e90407bd33d572241c49545aef26459d2950ac9ef83c11db18710a043f62",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/polkit-pkla-compat-0.1-21.el9.x86_64.rpm",
    ],
)

rpm(
    name = "popt-0__1.18-8.el9.aarch64",
    sha256 = "11636ccf4c42f8fd89d2ada61a382792ad560ac052e499d1b7193c3c8fab7637",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/p/popt-1.18-8.el9.aarch64.rpm",
    ],
)

rpm(
    name = "popt-0__1.18-8.el9.x86_64",
    sha256 = "4306e6bb950191170669ccbfe904bf943a94736e910179f9b0db962148fe4bcf",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/popt-1.18-8.el9.x86_64.rpm",
    ],
)

rpm(
    name = "procps-ng-0__3.3.17-13.el9.aarch64",
    sha256 = "933919c4139414315ed3bc9ca030dfc2804f8f18790bae378b3e083758c2ec28",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/p/procps-ng-3.3.17-13.el9.aarch64.rpm",
    ],
)

rpm(
    name = "procps-ng-0__3.3.17-13.el9.x86_64",
    sha256 = "b82c86c32069bd67a90c25bf07576242a0d669d5b17105bbd55998ab5a8c46f3",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/procps-ng-3.3.17-13.el9.x86_64.rpm",
    ],
)

rpm(
    name = "protobuf-c-0__1.3.3-13.el9.aarch64",
    sha256 = "392e4853776c93521ce1d81921762b300e18ad7ca65c5415716cc3af076a7fd1",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/p/protobuf-c-1.3.3-13.el9.aarch64.rpm",
    ],
)

rpm(
    name = "protobuf-c-0__1.3.3-13.el9.x86_64",
    sha256 = "084e207869fa9bfd0c4c94e4be1249aa909087fe90229141149b95e517ab74cf",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/protobuf-c-1.3.3-13.el9.x86_64.rpm",
    ],
)

rpm(
    name = "psmisc-0__23.4-3.el9.aarch64",
    sha256 = "e12449b4349de38d20c4e65d5bddef5aeea31cd010d4f60cb9d13b0df30dbeb2",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/p/psmisc-23.4-3.el9.aarch64.rpm",
    ],
)

rpm(
    name = "psmisc-0__23.4-3.el9.x86_64",
    sha256 = "c6bb80487a9518ffd9956018f7577f93d011d28077ca4453a97701a181269745",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/psmisc-23.4-3.el9.x86_64.rpm",
    ],
)

rpm(
    name = "publicsuffix-list-dafsa-0__20210518-3.el9.x86_64",
    sha256 = "e21742695de260517bfa5340aaab1360d936b20cd9896ab79ed74e74a0949eb2",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/publicsuffix-list-dafsa-20210518-3.el9.noarch.rpm",
    ],
)

rpm(
    name = "python3-0__3.9.18-1.el9_3.1.aarch64",
    sha256 = "1c6ef0beb29a2ee6e9694e1a31da53f184083301c96b9e88fdf6a6b32ea696a9",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/p/python3-3.9.18-1.el9_3.1.aarch64.rpm",
    ],
)

rpm(
    name = "python3-0__3.9.18-1.el9_3.1.x86_64",
    sha256 = "09709555500f9a3ca38d8a3301e5464c0bb28724dea590553d6cf619b8368b31",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/python3-3.9.18-1.el9_3.1.x86_64.rpm",
    ],
)

rpm(
    name = "python3-configshell-1__1.1.28-7.el9.aarch64",
    sha256 = "5fef8514c1ca02661f8af4d56bfd0e63a82918777fd0049a9762cd81a5b555f6",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/p/python3-configshell-1.1.28-7.el9.noarch.rpm",
    ],
)

rpm(
    name = "python3-configshell-1__1.1.28-7.el9.x86_64",
    sha256 = "5fef8514c1ca02661f8af4d56bfd0e63a82918777fd0049a9762cd81a5b555f6",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/python3-configshell-1.1.28-7.el9.noarch.rpm",
    ],
)

rpm(
    name = "python3-dbus-0__1.2.18-2.el9.aarch64",
    sha256 = "dd6d2a5a5b62d44a96a7358a488a14b306f0dad3bf3b10b95ac841be42474c4f",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/p/python3-dbus-1.2.18-2.el9.aarch64.rpm",
    ],
)

rpm(
    name = "python3-dbus-0__1.2.18-2.el9.x86_64",
    sha256 = "e23e3586da45903370df716592dc57e6a2a9d8affe0bc28aa71a7009b8ad4e53",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/python3-dbus-1.2.18-2.el9.x86_64.rpm",
    ],
)

rpm(
    name = "python3-gobject-base-0__3.40.1-6.el9.aarch64",
    sha256 = "667e6d62393ca33e69fd996b4d2ae542135595b0b8d88eb19b1278747d5f1d73",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/p/python3-gobject-base-3.40.1-6.el9.aarch64.rpm",
    ],
)

rpm(
    name = "python3-gobject-base-0__3.40.1-6.el9.x86_64",
    sha256 = "d7e1edfadf0efe52373d0c928a73d54a54495314cdac0c024c5e4975c02ccfea",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/python3-gobject-base-3.40.1-6.el9.x86_64.rpm",
    ],
)

rpm(
    name = "python3-gobject-base-noarch-0__3.40.1-6.el9.aarch64",
    sha256 = "b2dad2251c850ea5dd1e7488af0054d9ff5452af23e557d4fed71e7af3e10308",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/p/python3-gobject-base-noarch-3.40.1-6.el9.noarch.rpm",
    ],
)

rpm(
    name = "python3-gobject-base-noarch-0__3.40.1-6.el9.x86_64",
    sha256 = "b2dad2251c850ea5dd1e7488af0054d9ff5452af23e557d4fed71e7af3e10308",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/python3-gobject-base-noarch-3.40.1-6.el9.noarch.rpm",
    ],
)

rpm(
    name = "python3-kmod-0__0.9-32.el9.0.1.aarch64",
    sha256 = "dd5fcf99a9a86a4b6f9bc259d1134754d3f55ae3e79e11839dc023feb515c89e",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/p/python3-kmod-0.9-32.el9.0.1.aarch64.rpm",
    ],
)

rpm(
    name = "python3-kmod-0__0.9-32.el9.0.1.x86_64",
    sha256 = "0b6ddb50bfaa129db23eda7c0aebfdc40e5c5950a3aa11085262d9bf2a439423",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/python3-kmod-0.9-32.el9.0.1.x86_64.rpm",
    ],
)

rpm(
    name = "python3-libs-0__3.9.18-1.el9_3.1.aarch64",
    sha256 = "f1850984c8d676217bfeb06b88e74195a2f30de325053d1eb3a8ba58307ebbbd",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/p/python3-libs-3.9.18-1.el9_3.1.aarch64.rpm",
    ],
)

rpm(
    name = "python3-libs-0__3.9.18-1.el9_3.1.x86_64",
    sha256 = "7d4284e7081de8475155dafd908ac42265e975a814545793e60a643d74c85a53",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/python3-libs-3.9.18-1.el9_3.1.x86_64.rpm",
    ],
)

rpm(
    name = "python3-pip-wheel-0__21.2.3-7.el9_3.1.aarch64",
    sha256 = "3ba7a97fe99cd6bb423c3d979bfd47a728df85f104beb2a06c3a7528b5d659cb",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/p/python3-pip-wheel-21.2.3-7.el9_3.1.noarch.rpm",
    ],
)

rpm(
    name = "python3-pip-wheel-0__21.2.3-7.el9_3.1.x86_64",
    sha256 = "3ba7a97fe99cd6bb423c3d979bfd47a728df85f104beb2a06c3a7528b5d659cb",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/python3-pip-wheel-21.2.3-7.el9_3.1.noarch.rpm",
    ],
)

rpm(
    name = "python3-pyparsing-0__2.4.7-9.el9.aarch64",
    sha256 = "40ef3b8d201e07ac5a339334d7c8ae15a024aa6b4783504a265efca0c2b60b27",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/p/python3-pyparsing-2.4.7-9.el9.noarch.rpm",
    ],
)

rpm(
    name = "python3-pyparsing-0__2.4.7-9.el9.x86_64",
    sha256 = "9fa0091a1c1e9cded3dbcceadb327ee51ca7ca93fadc0e7763f214ca0ca6b735",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/python3-pyparsing-2.4.7-9.el9.noarch.rpm",
    ],
)

rpm(
    name = "python3-pyudev-0__0.22.0-6.el9.aarch64",
    sha256 = "3b6b79b5b1e14de93b102ab2ca8a30a61a2e479636363c775caba019803938a1",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/p/python3-pyudev-0.22.0-6.el9.noarch.rpm",
    ],
)

rpm(
    name = "python3-pyudev-0__0.22.0-6.el9.x86_64",
    sha256 = "f80c7b0e6211747b80d86db522435e8eed74137b10226770fd55e078d5eb52b7",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/python3-pyudev-0.22.0-6.el9.noarch.rpm",
    ],
)

rpm(
    name = "python3-rtslib-0__2.1.75-1.el9.aarch64",
    sha256 = "cb61cc1b08659c5a9e188dd3b235d68409a78a8b68d40c58cb1242e22c811bc8",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/p/python3-rtslib-2.1.75-1.el9.noarch.rpm",
    ],
)

rpm(
    name = "python3-rtslib-0__2.1.75-1.el9.x86_64",
    sha256 = "cb61cc1b08659c5a9e188dd3b235d68409a78a8b68d40c58cb1242e22c811bc8",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/p/python3-rtslib-2.1.75-1.el9.noarch.rpm",
    ],
)

rpm(
    name = "python3-setuptools-wheel-0__53.0.0-12.el9.aarch64",
    sha256 = "5bb20fbfab730d4a064f89492fddb394fc811070fed89015a2f84e700e6db276",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/p/python3-setuptools-wheel-53.0.0-12.el9.noarch.rpm",
    ],
)

rpm(
    name = "python3-setuptools-wheel-0__53.0.0-12.el9.x86_64",
    sha256 = "5bb20fbfab730d4a064f89492fddb394fc811070fed89015a2f84e700e6db276",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/python3-setuptools-wheel-53.0.0-12.el9.noarch.rpm",
    ],
)

rpm(
    name = "python3-six-0__1.15.0-9.el9.aarch64",
    sha256 = "752fc8b137a10cedd07c59478bd0822830d7502b7ce6d5cbb5c5f8cb5b4f1f1c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/p/python3-six-1.15.0-9.el9.noarch.rpm",
    ],
)

rpm(
    name = "python3-six-0__1.15.0-9.el9.x86_64",
    sha256 = "752fc8b137a10cedd07c59478bd0822830d7502b7ce6d5cbb5c5f8cb5b4f1f1c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/python3-six-1.15.0-9.el9.noarch.rpm",
    ],
)

rpm(
    name = "python3-urwid-0__2.1.2-4.el9.aarch64",
    sha256 = "0f500c0e96f167433c246b4df4ea1954a30983119b4aff9bff9398ca473be5b6",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/p/python3-urwid-2.1.2-4.el9.aarch64.rpm",
    ],
)

rpm(
    name = "python3-urwid-0__2.1.2-4.el9.x86_64",
    sha256 = "3e59948519fb95c8c5138dec9ac0951a03e804d19feee17785d1d1eef35921b0",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/p/python3-urwid-2.1.2-4.el9.x86_64.rpm",
    ],
)

rpm(
    name = "qemu-img-17__8.0.0-16.el9_3.3.aarch64",
    sha256 = "f1bb61a7dbedabf5b2e6e51ae5120acbe676bdaeb554e74d7c9d85d2134078bc",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/q/qemu-img-8.0.0-16.el9_3.3.aarch64.rpm",
    ],
)

rpm(
    name = "qemu-img-17__8.0.0-16.el9_3.3.x86_64",
    sha256 = "235efdb00d531145c0835008fcc77c54c24e2b3c72ef7916cad84cdfb5bafe98",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/q/qemu-img-8.0.0-16.el9_3.3.x86_64.rpm",
    ],
)

rpm(
    name = "qemu-kvm-common-17__8.0.0-16.el9_3.3.aarch64",
    sha256 = "89c9403890ffc932307e9f048afe238f36e23da70de45c0742d60b4db37055c7",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/q/qemu-kvm-common-8.0.0-16.el9_3.3.aarch64.rpm",
    ],
)

rpm(
    name = "qemu-kvm-common-17__8.0.0-16.el9_3.3.x86_64",
    sha256 = "d25761e7cfb947140d84f88f4308c6a04c371b5dc7d33c427edcdb6d35a5981f",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/q/qemu-kvm-common-8.0.0-16.el9_3.3.x86_64.rpm",
    ],
)

rpm(
    name = "qemu-kvm-core-17__8.0.0-16.el9_3.3.aarch64",
    sha256 = "b6f609983cef495f2f436c30ee4f7c7bf99924d27e64ffe2e8618810d644cc5b",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/q/qemu-kvm-core-8.0.0-16.el9_3.3.aarch64.rpm",
    ],
)

rpm(
    name = "qemu-kvm-core-17__8.0.0-16.el9_3.3.x86_64",
    sha256 = "5bf4aab9e2aac5e9683a0f415aec39a644b6508fc792c4c17202a30ced30efad",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/q/qemu-kvm-core-8.0.0-16.el9_3.3.x86_64.rpm",
    ],
)

rpm(
    name = "qemu-kvm-device-display-virtio-gpu-17__8.0.0-16.el9_3.3.aarch64",
    sha256 = "d91e638faa6da2933493c93ebe5591f06dde911641ed96a8cb37ffb9617485ac",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/q/qemu-kvm-device-display-virtio-gpu-8.0.0-16.el9_3.3.aarch64.rpm",
    ],
)

rpm(
    name = "qemu-kvm-device-display-virtio-gpu-pci-17__8.0.0-16.el9_3.3.aarch64",
    sha256 = "1633f0646f2644688dcda85bf36ed4de635c0516f15e0dc3ccea5a29ff0ff379",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/q/qemu-kvm-device-display-virtio-gpu-pci-8.0.0-16.el9_3.3.aarch64.rpm",
    ],
)

rpm(
    name = "qemu-kvm-device-usb-host-17__8.0.0-16.el9_3.3.aarch64",
    sha256 = "9ea4aa97150d5dfb62ba00ff04936d13a1e6eed6d998b82a91efcb6ea76baf7c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/q/qemu-kvm-device-usb-host-8.0.0-16.el9_3.3.aarch64.rpm",
    ],
)

rpm(
    name = "qemu-kvm-device-usb-host-17__8.0.0-16.el9_3.3.x86_64",
    sha256 = "844455237f3e3043c2968913145c5155b24509d8880913d9e8af8391d4b76572",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/q/qemu-kvm-device-usb-host-8.0.0-16.el9_3.3.x86_64.rpm",
    ],
)

rpm(
    name = "qemu-kvm-device-usb-redirect-17__8.0.0-16.el9_3.3.x86_64",
    sha256 = "f7d1a20c14e1a338a060152dafa8d76661965e784880425a81ae53c399077d76",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/q/qemu-kvm-device-usb-redirect-8.0.0-16.el9_3.3.x86_64.rpm",
    ],
)

rpm(
    name = "qemu-pr-helper-17__8.0.0-16.el9_3.3.aarch64",
    sha256 = "b430fb34b3da6ee54e17bd8b1010a24e955fcb74075d5938141081478fbab4eb",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/q/qemu-pr-helper-8.0.0-16.el9_3.3.aarch64.rpm",
    ],
)

rpm(
    name = "qemu-pr-helper-17__8.0.0-16.el9_3.3.x86_64",
    sha256 = "b83b9c0b80b19ddad562bdce640f15d4e73081dd90bd5aa343ea110d6bbbccc2",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/q/qemu-pr-helper-8.0.0-16.el9_3.3.x86_64.rpm",
    ],
)

rpm(
    name = "quota-1__4.06-6.el9.x86_64",
    sha256 = "f67ab8beded96c1202a02d3a78599abb8923b886d69cd78239920259f08550cc",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/q/quota-4.06-6.el9.x86_64.rpm",
    ],
)

rpm(
    name = "quota-nls-1__4.06-6.el9.x86_64",
    sha256 = "559f42980ccf87eb65f3d447761acfea03f234ddd003a4c833721f7f72d60371",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/q/quota-nls-4.06-6.el9.noarch.rpm",
    ],
)

rpm(
    name = "readline-0__8.1-4.el9.aarch64",
    sha256 = "f9524ba04a382ef9595d66ed84cdda3c36e1e651da17d6552e7d0ef0348ea1d5",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/r/readline-8.1-4.el9.aarch64.rpm",
    ],
)

rpm(
    name = "readline-0__8.1-4.el9.x86_64",
    sha256 = "b85f5cffef627afe640cf7405845cb45956d66ef5a06e7c48dc7da47a7191674",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/r/readline-8.1-4.el9.x86_64.rpm",
    ],
)

rpm(
    name = "rocky-gpg-keys-0__9.3-1.3.el9.aarch64",
    sha256 = "4002d66aa28a77ac141b101fc5fa345207c814349e8d2e5d803c20cc89cfa712",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/r/rocky-gpg-keys-9.3-1.3.el9.noarch.rpm",
    ],
)

rpm(
    name = "rocky-gpg-keys-0__9.3-1.3.el9.x86_64",
    sha256 = "4002d66aa28a77ac141b101fc5fa345207c814349e8d2e5d803c20cc89cfa712",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/r/rocky-gpg-keys-9.3-1.3.el9.noarch.rpm",
    ],
)

rpm(
    name = "rocky-release-0__9.3-1.3.el9.aarch64",
    sha256 = "65148a25a2f9a96e8dfa502c486a4b82233601328bc2ba7730cc9b661a70e0bf",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/r/rocky-release-9.3-1.3.el9.noarch.rpm",
    ],
)

rpm(
    name = "rocky-release-0__9.3-1.3.el9.x86_64",
    sha256 = "65148a25a2f9a96e8dfa502c486a4b82233601328bc2ba7730cc9b661a70e0bf",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/r/rocky-release-9.3-1.3.el9.noarch.rpm",
    ],
)

rpm(
    name = "rocky-repos-0__9.3-1.3.el9.aarch64",
    sha256 = "56273da27e20b0624aef60ae8a43258e6df1009aa401cb1e0f6fdfbdd39ae4c1",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/r/rocky-repos-9.3-1.3.el9.noarch.rpm",
    ],
)

rpm(
    name = "rocky-repos-0__9.3-1.3.el9.x86_64",
    sha256 = "56273da27e20b0624aef60ae8a43258e6df1009aa401cb1e0f6fdfbdd39ae4c1",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/r/rocky-repos-9.3-1.3.el9.noarch.rpm",
    ],
)

rpm(
    name = "rpcbind-0__1.2.6-5.el9.x86_64",
    sha256 = "96ebf3804e5574010ed0fa809b7140fc1968419fe1468e75de3146c3d0ad976f",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/r/rpcbind-1.2.6-5.el9.x86_64.rpm",
    ],
)

rpm(
    name = "rpm-0__4.16.1.3-27.el9_3.aarch64",
    sha256 = "224df70ad2dd5d0393e834b6c39dbb337bf72def8d15d9a12d2c8a9aee8e2cdf",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/r/rpm-4.16.1.3-27.el9_3.aarch64.rpm",
    ],
)

rpm(
    name = "rpm-0__4.16.1.3-27.el9_3.x86_64",
    sha256 = "7ea9e8bc8387169634a3cfcc38f79226ab7c8ecaf5ad124db44cf82fba5f2821",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/r/rpm-4.16.1.3-27.el9_3.x86_64.rpm",
    ],
)

rpm(
    name = "rpm-libs-0__4.16.1.3-27.el9_3.aarch64",
    sha256 = "9cf0274b05359cd40ea668e741c67ce516815fb438541e1ccd84973ee4527012",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/r/rpm-libs-4.16.1.3-27.el9_3.aarch64.rpm",
    ],
)

rpm(
    name = "rpm-libs-0__4.16.1.3-27.el9_3.x86_64",
    sha256 = "37c05c94daa2ff81207273f016028f9770887bd4faeb443d17f7f9674e3b374d",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/r/rpm-libs-4.16.1.3-27.el9_3.x86_64.rpm",
    ],
)

rpm(
    name = "rpm-plugin-selinux-0__4.16.1.3-27.el9_3.aarch64",
    sha256 = "b5553827727c5f8ca43617e986e1ad4667e7f8b9b2ba9408a213c995c99d6c9c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/r/rpm-plugin-selinux-4.16.1.3-27.el9_3.aarch64.rpm",
    ],
)

rpm(
    name = "rpm-plugin-selinux-0__4.16.1.3-27.el9_3.x86_64",
    sha256 = "17125a66c95fc91e0b23d17526b009b1aa266b6539171d1507cc4bb0564e19fb",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/r/rpm-plugin-selinux-4.16.1.3-27.el9_3.x86_64.rpm",
    ],
)

rpm(
    name = "seabios-0__1.16.1-1.el9.x86_64",
    sha256 = "399d57eb82eec042d053daf2ae126fbb6f204500a344f5f6c2ed748e99d65b35",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/s/seabios-1.16.1-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "seabios-bin-0__1.16.1-1.el9.x86_64",
    sha256 = "0434002fa394016a5eb6db2ba9dfd5bf1665d20992c701155f311950a1cf6ff2",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/s/seabios-bin-1.16.1-1.el9.noarch.rpm",
    ],
)

rpm(
    name = "seavgabios-bin-0__1.16.1-1.el9.x86_64",
    sha256 = "6183a9127ee5e5920bcda81d72679005809d5599ed655ae2c164f9ce36a8f8f6",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/s/seavgabios-bin-1.16.1-1.el9.noarch.rpm",
    ],
)

rpm(
    name = "sed-0__4.8-9.el9.aarch64",
    sha256 = "b48959916662d4d20a6207e02f7e243408987d99621963d450d0bec185cffbfe",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/s/sed-4.8-9.el9.aarch64.rpm",
    ],
)

rpm(
    name = "sed-0__4.8-9.el9.x86_64",
    sha256 = "005c959166838b0e45f02e699c35ec5449025e2463751c56b7e614bbd9514732",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/s/sed-4.8-9.el9.x86_64.rpm",
    ],
)

rpm(
    name = "selinux-policy-0__38.1.23-1.el9_3.2.aarch64",
    sha256 = "35852b3d90160e23019cce8ea87736b5e23f035781633d90bd969917e42d8d3c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/s/selinux-policy-38.1.23-1.el9_3.2.noarch.rpm",
    ],
)

rpm(
    name = "selinux-policy-0__38.1.23-1.el9_3.2.x86_64",
    sha256 = "35852b3d90160e23019cce8ea87736b5e23f035781633d90bd969917e42d8d3c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/s/selinux-policy-38.1.23-1.el9_3.2.noarch.rpm",
    ],
)

rpm(
    name = "selinux-policy-targeted-0__38.1.23-1.el9_3.2.aarch64",
    sha256 = "010743b38760602cc9c12d8c63d81415318faa06204efa4825a0d6ca2608a87c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/s/selinux-policy-targeted-38.1.23-1.el9_3.2.noarch.rpm",
    ],
)

rpm(
    name = "selinux-policy-targeted-0__38.1.23-1.el9_3.2.x86_64",
    sha256 = "010743b38760602cc9c12d8c63d81415318faa06204efa4825a0d6ca2608a87c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/s/selinux-policy-targeted-38.1.23-1.el9_3.2.noarch.rpm",
    ],
)

rpm(
    name = "setup-0__2.13.7-9.el9.aarch64",
    sha256 = "d6a656fedcb0a6706ba20bc8131833b0481fcc277a1a57e17d1225e34a553d34",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/s/setup-2.13.7-9.el9.noarch.rpm",
    ],
)

rpm(
    name = "setup-0__2.13.7-9.el9.x86_64",
    sha256 = "d6a656fedcb0a6706ba20bc8131833b0481fcc277a1a57e17d1225e34a553d34",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/s/setup-2.13.7-9.el9.noarch.rpm",
    ],
)

rpm(
    name = "sevctl-0__0.4.2-1.el9.x86_64",
    sha256 = "b66a995b5e5213d2a4e69aafb6a7e95154536474bf83a142735e214118d57ebb",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/s/sevctl-0.4.2-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "shadow-utils-2__4.9-8.el9.aarch64",
    sha256 = "73422bb56437e1e6cb7a26770688281ab07e7976993a944e6f7739fe79db7d1a",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/s/shadow-utils-4.9-8.el9.aarch64.rpm",
    ],
)

rpm(
    name = "shadow-utils-2__4.9-8.el9.x86_64",
    sha256 = "5ccdca4c6840b5e7944df911f0bc0f29657499630b866ab9d7944d153d0d401c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/s/shadow-utils-4.9-8.el9.x86_64.rpm",
    ],
)

rpm(
    name = "snappy-0__1.1.8-8.el9.aarch64",
    sha256 = "821877ab14ad8a15a38999cab3a408145e42414c7ed7620f689e0e648d87e080",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/s/snappy-1.1.8-8.el9.aarch64.rpm",
    ],
)

rpm(
    name = "snappy-0__1.1.8-8.el9.x86_64",
    sha256 = "015cc069208f232ae50267e76bca2410d187dbe8d044f15424857d324d45bc89",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/s/snappy-1.1.8-8.el9.x86_64.rpm",
    ],
)

rpm(
    name = "sqlite-libs-0__3.34.1-7.el9_3.aarch64",
    sha256 = "2cb657f0cbcac497228fec8d29621f7e093af3a0b59a7d78703eb59032fb40a8",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/s/sqlite-libs-3.34.1-7.el9_3.aarch64.rpm",
    ],
)

rpm(
    name = "sqlite-libs-0__3.34.1-7.el9_3.x86_64",
    sha256 = "9e9b58febeff10765c104ecebc8af189507ecd6c2a600f9b0d9207394117a063",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/s/sqlite-libs-3.34.1-7.el9_3.x86_64.rpm",
    ],
)

rpm(
    name = "sssd-client-0__2.9.1-4.el9_3.5.aarch64",
    sha256 = "0928917e62fb4fe86800339d10c20595b050b2c66b6b48078e680775cbc6e1ad",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/s/sssd-client-2.9.1-4.el9_3.5.aarch64.rpm",
    ],
)

rpm(
    name = "sssd-client-0__2.9.1-4.el9_3.5.x86_64",
    sha256 = "b5d393bbdb4993e3f44bde1a8da934be325f51abcfe2df572962a75b76d12e00",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/s/sssd-client-2.9.1-4.el9_3.5.x86_64.rpm",
    ],
)

rpm(
    name = "swtpm-0__0.8.0-1.el9.aarch64",
    sha256 = "41893a90c7e464b2d12e50ef3e586c6cb8246555bb34d7575f1003cf18a4c139",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/s/swtpm-0.8.0-1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "swtpm-0__0.8.0-1.el9.x86_64",
    sha256 = "5eb01dd8584a5049fe99ca0bae3a344c2ac1209bd16ae5e6c7affbcb6d54ea1c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/s/swtpm-0.8.0-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "swtpm-libs-0__0.8.0-1.el9.aarch64",
    sha256 = "26afd2a0ec3e7594eb091c04a7edcd5d7d55ae34157b15d67292eec083e407d1",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/s/swtpm-libs-0.8.0-1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "swtpm-libs-0__0.8.0-1.el9.x86_64",
    sha256 = "10e022aec0504ea5429d99e5f33baea9f278c1ee43bd4dd012a5cbeb4a5f0e48",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/s/swtpm-libs-0.8.0-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "swtpm-tools-0__0.8.0-1.el9.aarch64",
    sha256 = "d0cdb9db3f699a7222085b8987cfd4dde7925dc9b038962b5ab2983053756a0a",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/s/swtpm-tools-0.8.0-1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "swtpm-tools-0__0.8.0-1.el9.x86_64",
    sha256 = "e0e25c30526267a12c61655d6437ce906bc25c1ab2dd3ba22bb856fad5dd961c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/s/swtpm-tools-0.8.0-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "systemd-0__252-18.el9.0.1.rocky.aarch64",
    sha256 = "64e08250ba00c61f3ec88b8063fee6e16a1a02f6fdcd63484afab2d517c919fe",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/s/systemd-252-18.el9.0.1.rocky.aarch64.rpm",
    ],
)

rpm(
    name = "systemd-0__252-18.el9.0.1.rocky.x86_64",
    sha256 = "a5aa14cbdd3af530e92fc7947edbe52f60b9d767bb5ba81b26909274b93e706c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/s/systemd-252-18.el9.0.1.rocky.x86_64.rpm",
    ],
)

rpm(
    name = "systemd-container-0__252-18.el9.0.1.rocky.aarch64",
    sha256 = "5173ab6a5c34123fdaad834f617f074e0ac0a58a3508453b58551ae4ace0a9f9",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/s/systemd-container-252-18.el9.0.1.rocky.aarch64.rpm",
    ],
)

rpm(
    name = "systemd-container-0__252-18.el9.0.1.rocky.x86_64",
    sha256 = "fb1fbd42f804b814cadb5e86a15d0dbc9d68de65834943b214de426caadf6489",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/s/systemd-container-252-18.el9.0.1.rocky.x86_64.rpm",
    ],
)

rpm(
    name = "systemd-libs-0__252-18.el9.0.1.rocky.aarch64",
    sha256 = "99b14c6dfe29cc9c04862c8a61f4d92bd24c9d34863e9d5c8ab39caa3902761b",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/s/systemd-libs-252-18.el9.0.1.rocky.aarch64.rpm",
    ],
)

rpm(
    name = "systemd-libs-0__252-18.el9.0.1.rocky.x86_64",
    sha256 = "96959d8e10651cd021f9b2e3e86f3f65ab4dbb817f9059e213b52e09115e199b",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/s/systemd-libs-252-18.el9.0.1.rocky.x86_64.rpm",
    ],
)

rpm(
    name = "systemd-pam-0__252-18.el9.0.1.rocky.aarch64",
    sha256 = "b2f7b6e169d18ff83e7a0a55a7a2c7d6b966759962d956f0c640cc5fb03bac6c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/s/systemd-pam-252-18.el9.0.1.rocky.aarch64.rpm",
    ],
)

rpm(
    name = "systemd-pam-0__252-18.el9.0.1.rocky.x86_64",
    sha256 = "33e84099762fd48b7f23c1be240c5fcdfd0f4b54e6252e36e0b39c1ad3a9c5b2",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/s/systemd-pam-252-18.el9.0.1.rocky.x86_64.rpm",
    ],
)

rpm(
    name = "systemd-rpm-macros-0__252-18.el9.0.1.rocky.aarch64",
    sha256 = "4b421d3dc3284b183cc7ef7afce0d1e0c14bc3a29fd0311608a203d42403e0c8",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/s/systemd-rpm-macros-252-18.el9.0.1.rocky.noarch.rpm",
    ],
)

rpm(
    name = "systemd-rpm-macros-0__252-18.el9.0.1.rocky.x86_64",
    sha256 = "4b421d3dc3284b183cc7ef7afce0d1e0c14bc3a29fd0311608a203d42403e0c8",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/s/systemd-rpm-macros-252-18.el9.0.1.rocky.noarch.rpm",
    ],
)

rpm(
    name = "tar-2__1.34-6.el9_1.aarch64",
    sha256 = "6e5bf8c10468082774b189468c4d0f0ea18d500dd2d1c461f44eead55f7f1867",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/t/tar-1.34-6.el9_1.aarch64.rpm",
    ],
)

rpm(
    name = "tar-2__1.34-6.el9_1.x86_64",
    sha256 = "0021b9ea1115a020b1a007d033b29b5efe2715970ff35466247863db7561c08f",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/t/tar-1.34-6.el9_1.x86_64.rpm",
    ],
)

rpm(
    name = "target-restore-0__2.1.75-1.el9.aarch64",
    sha256 = "1e6d0e3382703875fb33f4ddeeff009875657a38de1f53b4233e02d4794ae463",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/t/target-restore-2.1.75-1.el9.noarch.rpm",
    ],
)

rpm(
    name = "target-restore-0__2.1.75-1.el9.x86_64",
    sha256 = "1e6d0e3382703875fb33f4ddeeff009875657a38de1f53b4233e02d4794ae463",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/t/target-restore-2.1.75-1.el9.noarch.rpm",
    ],
)

rpm(
    name = "targetcli-0__2.1.53-7.el9.aarch64",
    sha256 = "a1f620ccef942499d36e94804a5b746ef739437450bb4cbaea55a146b4627a3b",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/t/targetcli-2.1.53-7.el9.noarch.rpm",
    ],
)

rpm(
    name = "targetcli-0__2.1.53-7.el9.x86_64",
    sha256 = "b42866fd04e52979638aa1f51a369b563446b50ab4dbf821d0ed2850b9c3648f",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/t/targetcli-2.1.53-7.el9.noarch.rpm",
    ],
)

rpm(
    name = "tzdata-0__2024a-1.el9.aarch64",
    sha256 = "02b97ca307e83d3c4f00e7e57f315e1f25949313ea98b704efef07553b52b1aa",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/t/tzdata-2024a-1.el9.noarch.rpm",
    ],
)

rpm(
    name = "tzdata-0__2024a-1.el9.x86_64",
    sha256 = "02b97ca307e83d3c4f00e7e57f315e1f25949313ea98b704efef07553b52b1aa",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/t/tzdata-2024a-1.el9.noarch.rpm",
    ],
)

rpm(
    name = "unbound-libs-0__1.16.2-3.el9_3.5.aarch64",
    sha256 = "c4edb6c5acdd60fd0cbb8637d0dbf3c5cdff28195664b4e80c82afca7731d736",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/u/unbound-libs-1.16.2-3.el9_3.5.aarch64.rpm",
    ],
)

rpm(
    name = "unbound-libs-0__1.16.2-3.el9_3.5.x86_64",
    sha256 = "1e87341a97cc10cf26d45c6e766061f51ccdd2dc65ce149821de5152948850dc",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/u/unbound-libs-1.16.2-3.el9_3.5.x86_64.rpm",
    ],
)

rpm(
    name = "usbredir-0__0.13.0-2.el9.x86_64",
    sha256 = "b2b8b6419454e86d27ee9d19409fffeec4097845f3798f12c9741f459c8d8ccc",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/u/usbredir-0.13.0-2.el9.x86_64.rpm",
    ],
)

rpm(
    name = "userspace-rcu-0__0.12.1-6.el9.aarch64",
    sha256 = "bfcd84d373911a26b5c05284dd01cf7a3115506852275d3683975a285157b712",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/u/userspace-rcu-0.12.1-6.el9.aarch64.rpm",
    ],
)

rpm(
    name = "userspace-rcu-0__0.12.1-6.el9.x86_64",
    sha256 = "9115f3ec621316ccc39d7dbf09652236316f348d4c33d295eddf5a50080c0eef",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/u/userspace-rcu-0.12.1-6.el9.x86_64.rpm",
    ],
)

rpm(
    name = "util-linux-0__2.37.4-15.el9.aarch64",
    sha256 = "415e76704013d14085e88ccb15034f54a5f167ca8d41f2b14b9eb03de44ed680",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/u/util-linux-2.37.4-15.el9.aarch64.rpm",
    ],
)

rpm(
    name = "util-linux-0__2.37.4-15.el9.x86_64",
    sha256 = "33fb10e25c04cae3890fb061be702c810960017e3b5fb6b90ddd84d6031938e3",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/u/util-linux-2.37.4-15.el9.x86_64.rpm",
    ],
)

rpm(
    name = "util-linux-core-0__2.37.4-15.el9.aarch64",
    sha256 = "4035acf97dbceea1bca91215585e72a81e12623cdcae6013aec6384b04c8fb80",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/u/util-linux-core-2.37.4-15.el9.aarch64.rpm",
    ],
)

rpm(
    name = "util-linux-core-0__2.37.4-15.el9.x86_64",
    sha256 = "0adabd5a00aa01e4abd11a1d8600a71163f8aeee42b1d28b97af207425094689",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/u/util-linux-core-2.37.4-15.el9.x86_64.rpm",
    ],
)

rpm(
    name = "vim-minimal-2__8.2.2637-20.el9_1.aarch64",
    sha256 = "3f19e1f3fc6078844794b149ea4d4054bea37ea2d18da67d4062a3ce4589ae59",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/v/vim-minimal-8.2.2637-20.el9_1.aarch64.rpm",
    ],
)

rpm(
    name = "vim-minimal-2__8.2.2637-20.el9_1.x86_64",
    sha256 = "31283683ce783f3eecf072d790ef9abd010ba26333f528a7a55fa1ea168301d1",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/v/vim-minimal-8.2.2637-20.el9_1.x86_64.rpm",
    ],
)

rpm(
    name = "virtiofsd-0__1.7.2-1.el9.aarch64",
    sha256 = "e5adc2939e545456e8811018f3a174e8b43625589d123f70e9098e440ee6a36e",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/v/virtiofsd-1.7.2-1.el9.aarch64.rpm",
    ],
)

rpm(
    name = "virtiofsd-0__1.7.2-1.el9.x86_64",
    sha256 = "b75a1d35984047e39414b78a44d36dfc8c00384942eb4dc3dcb767574eb4b46d",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/v/virtiofsd-1.7.2-1.el9.x86_64.rpm",
    ],
)

rpm(
    name = "which-0__2.21-29.el9.aarch64",
    sha256 = "e9351855af75aac7fb5c53173f262e4f87f400d7a96d48ec100a8d35269a1367",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/w/which-2.21-29.el9.aarch64.rpm",
    ],
)

rpm(
    name = "which-0__2.21-29.el9.x86_64",
    sha256 = "c54b2c55264430eee2786fad79bd26c7a7c62204b1f7b568e5f097d850db9688",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/w/which-2.21-29.el9.x86_64.rpm",
    ],
)

rpm(
    name = "xorriso-0__1.5.4-4.el9.aarch64",
    sha256 = "99bc95997e5a8f72b5ce7f0cd99aaabe16a49462a2762628ff403b316bcc835c",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/x/xorriso-1.5.4-4.el9.aarch64.rpm",
    ],
)

rpm(
    name = "xorriso-0__1.5.4-4.el9.x86_64",
    sha256 = "39a01394ae4e16a5a469881e5f4febf78a9811afdd95f4ca03b2a104958ad85d",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/x/xorriso-1.5.4-4.el9.x86_64.rpm",
    ],
)

rpm(
    name = "xz-0__5.2.5-8.el9_0.aarch64",
    sha256 = "7ad9c5e6425656499395a7da46c15df1e3392b8c2008803fc4da0ace5cc453b3",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/x/xz-5.2.5-8.el9_0.aarch64.rpm",
    ],
)

rpm(
    name = "xz-0__5.2.5-8.el9_0.x86_64",
    sha256 = "41043f1c47c48b956cfcc24f3640225120089fad47c87a954c81828ab77e7c46",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/x/xz-5.2.5-8.el9_0.x86_64.rpm",
    ],
)

rpm(
    name = "xz-libs-0__5.2.5-8.el9_0.aarch64",
    sha256 = "854a20a02aff28f4d116accb8833d9ce9e5acb0e682c8a43f65d786c4d154fca",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/x/xz-libs-5.2.5-8.el9_0.aarch64.rpm",
    ],
)

rpm(
    name = "xz-libs-0__5.2.5-8.el9_0.x86_64",
    sha256 = "7a6f5891537bbbf601ee574c5946c3f0f121369b85c6cdfdd07e974a4dc8d81d",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/x/xz-libs-5.2.5-8.el9_0.x86_64.rpm",
    ],
)

rpm(
    name = "yajl-0__2.1.0-22.el9.aarch64",
    sha256 = "e726409e886b3945715121e50d21351d60546ab8f49be9995d83e47cfa16a83f",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/aarch64/os/Packages/y/yajl-2.1.0-22.el9.aarch64.rpm",
    ],
)

rpm(
    name = "yajl-0__2.1.0-22.el9.x86_64",
    sha256 = "01f37c41e967b2c966ce4fec0de572168de96be5887ae2abd9b83b623e01e1f4",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/AppStream/x86_64/os/Packages/y/yajl-2.1.0-22.el9.x86_64.rpm",
    ],
)

rpm(
    name = "zlib-0__1.2.11-40.el9.aarch64",
    sha256 = "842cc46ca0ac7336264777679959edb656b1a928c38542bd633fe44367e555c1",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/aarch64/os/Packages/z/zlib-1.2.11-40.el9.aarch64.rpm",
    ],
)

rpm(
    name = "zlib-0__1.2.11-40.el9.x86_64",
    sha256 = "fcd8ca717c72aeb30ea69b4f892dc021e507d8835e7b03aff501cb094db083ea",
    urls = [
        "https://dl.rockylinux.org/vault/rocky/9.3/BaseOS/x86_64/os/Packages/z/zlib-1.2.11-40.el9.x86_64.rpm",
    ],
)
