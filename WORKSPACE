workspace(name = "backend-services")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

http_archive(
    name = "io_bazel_rules_go",
    sha256 = "d6b2513456fe2229811da7eb67a444be7785f5323c6708b38d851d2b51e54d83",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_go/releases/download/v0.30.0/rules_go-v0.30.0.zip",
        "https://github.com/bazelbuild/rules_go/releases/download/v0.30.0/rules_go-v0.30.0.zip",
    ],
)

load("@io_bazel_rules_go//go:deps.bzl", "go_register_toolchains", "go_rules_dependencies")

go_rules_dependencies()

go_register_toolchains(version = "1.17.1")

http_archive(
    name = "bazel_gazelle",
    sha256 = "32938bda16e6700063035479063d9d24c60eda8d79fd4739563f50d331cb3209",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/bazel-gazelle/releases/download/v0.35.0/bazel-gazelle-v0.35.0.tar.gz",
        "https://github.com/bazelbuild/bazel-gazelle/releases/download/v0.35.0/bazel-gazelle-v0.35.0.tar.gz",
    ],
)

load("@bazel_gazelle//:deps.bzl", "gazelle_dependencies")

gazelle_dependencies()

RULES_JVM_EXTERNAL_TAG = "4.1"

RULES_JVM_EXTERNAL_SHA = "f36441aa876c4f6427bfb2d1f2d723b48e9d930b62662bf723ddfb8fc80f0140"

http_archive(
    name = "rules_jvm_external",
    sha256 = RULES_JVM_EXTERNAL_SHA,
    strip_prefix = "rules_jvm_external-%s" % RULES_JVM_EXTERNAL_TAG,
    url = "https://github.com/bazelbuild/rules_jvm_external/archive/%s.zip" % RULES_JVM_EXTERNAL_TAG,
)

load("@rules_jvm_external//:defs.bzl", "maven_install")
load("@rules_jvm_external//:specs.bzl", "maven")

http_archive(
    name = "rules_spring",
    sha256 = "901462e6872f282636e3ca91f4976bc31e7024fb9760ddca2c9bac467b03d1db",
    urls = [
        "https://github.com/salesforce/rules_spring/releases/download/2.2.0/rules-spring-2.2.0.zip",
    ],
)

git_repository(
    name = "rules_proto",
    commit = "11bf7c25e666dd7ddacbcd4d4c4a9de7a25175f8",
    remote = "https://github.com/bazelbuild/rules_proto.git",
    shallow_since = "1637060833 +0100",
)

load("@rules_proto//proto:repositories.bzl", "rules_proto_dependencies", "rules_proto_toolchains")

rules_proto_dependencies()

rules_proto_toolchains()

# Protocol Buffers
load("@com_google_protobuf//:protobuf_deps.bzl", "protobuf_deps")

protobuf_deps()

http_archive(
    name = "rules_proto_grpc",
    sha256 = "507e38c8d95c7efa4f3b1c0595a8e8f139c885cb41a76cab7e20e4e67ae87731",
    strip_prefix = "rules_proto_grpc-4.1.1",
    urls = ["https://github.com/rules-proto-grpc/rules_proto_grpc/archive/4.1.1.tar.gz"],
)

load("@rules_proto_grpc//:repositories.bzl", "rules_proto_grpc_repos", "rules_proto_grpc_toolchains")

rules_proto_grpc_toolchains()

rules_proto_grpc_repos()

http_archive(
    name = "io_grpc_grpc_java",
    sha256 = "33775a1ad05974bbba6ff97801cd9b326485b21fab91b08a4e1bc53e500e6326",
    strip_prefix = "grpc-java-1.42.1",
    urls = ["https://github.com/grpc/grpc-java/archive/refs/tags/v1.42.1.tar.gz"],
)

load("@io_grpc_grpc_java//:repositories.bzl", "grpc_java_repositories")

grpc_java_repositories()

maven_install(
    artifacts = [
        "org.springframework.boot:spring-boot:2.6.1",
        "org.springframework.boot:spring-boot-dependencies:2.6.1",
        "org.springframework.boot:spring-boot-loader:2.6.1",
        "org.springframework.boot:spring-boot-starter:2.6.1",
        "org.springframework.boot:spring-boot-starter-web:2.6.1",
        "org.springframework.boot:spring-boot-starter-actuator:2.6.1",
        "org.springframework.boot:spring-boot-starter-data-jpa:2.6.1",
        "org.springframework.boot:spring-boot-starter-data-redis:2.6.1",
        "org.springframework.boot:spring-boot-starter-security:2.6.1",
        "org.springframework.boot:spring-boot-starter-validation:2.6.1",
        "org.springframework:spring-web:5.3.13",
        "org.springframework:spring-aspects:5.3.13",
        "org.springframework:spring-beans:5.3.13",
        "org.springframework:spring-context:5.3.13",
        "org.springframework.retry:spring-retry:1.3.1",
        "org.springframework.data:spring-data-jpa:2.5.6",
        "org.springframework.data:spring-data-elasticsearch:4.2.6",
        "org.springframework.security:spring-security-core:5.6.0",
        "org.json:json:20210307",
        "org.mockito:mockito-core:4.3.1",
        "org.assertj:assertj-core:3.21.0",
        "org.junit.jupiter:junit-jupiter-api:5.8.2",
        "org.junit.jupiter:junit-jupiter-engine:5.8.2",
        "org.junit.jupiter:junit-jupiter-params:5.8.2",
        "org.junit.platform:junit-platform-console:1.8.2",
        "net.devh:grpc-server-spring-boot-starter:2.13.0.RELEASE",
        "software.amazon.awssdk:s3:2.17.96",
        "net.logstash.logback:logstash-logback-encoder:7.0.1",
        "io.prometheus:simpleclient:0.12.0",
        "io.micrometer:micrometer-registry-prometheus:1.7.6",
        "io.sentry:sentry-spring-boot-starter:5.2.1",
        "io.sentry:sentry-logback:5.2.1",
        "org.slf4j:slf4j-api:1.7.32",
        "org.apache.commons:commons-lang3:3.12.0",
        "commons-validator:commons-validator:1.7",
        "commons-io:commons-io:2.11.0",
        "com.google.guava:guava:31.0.1-jre",
        "com.vladmihalcea:hibernate-types-52:2.14.0",
        "org.postgresql:postgresql:42.3.1",
        "org.flywaydb:flyway-core:7.15.0",
        "javax.annotation:javax.annotation-api:1.3.2",
        "javax.validation:validation-api:2.0.1.Final",
        "io.grpc:grpc-protobuf:1.42.1",
        "io.grpc:grpc-stub:1.42.1",
        "io.grpc:grpc-netty-shaded:1.42.1",
        "io.grpc:protoc-gen-grpc-java:1.42.1",
        "com.fasterxml.jackson.core:jackson-databind:2.13.0",
        "org.apache.httpcomponents:httpclient:4.5.13",
        "org.hibernate:hibernate-core:5.6.0.Final",
        "org.apache.commons:commons-csv:1.9.0",
        "commons-codec:commons-codec:1.15",
        "com.fasterxml.jackson.core:jackson-databind:2.13.0",
        "com.recombee:api-client:3.2.0",
        "com.sendgrid:sendgrid-java:4.8.0",
        "com.stripe:stripe-java:20.90.0",
        "org.springdoc:springdoc-openapi-ui:1.5.12",
        "org.springdoc:springdoc-openapi-data-rest:1.5.12",
        "com.auth0:java-jwt:3.18.2",
        "com.auth0:jwks-rsa:0.20.0",
        "com.google.protobuf:protoc:3.19.1",
        "com.amplitude:java-sdk:1.6.1",
        # Java GRPC
        "com.google.android:annotations:4.1.1.4",
        "com.google.api.grpc:proto-google-common-protos:2.6.0",
        "com.google.auth:google-auth-library-credentials:1.3.0",
        "com.google.auth:google-auth-library-oauth2-http:1.3.0",
        "com.google.code.findbugs:jsr305:3.0.2",
        "com.google.code.gson:gson:jar:2.8.9",
        "com.google.auto.value:auto-value:1.8.2",
        "com.google.auto.value:auto-value-annotations:1.8.2",
        "com.google.errorprone:error_prone_annotations:2.10.0",
        "com.google.guava:failureaccess:1.0.1",
        "com.google.guava:guava:31.0.1-jre",
        "com.google.j2objc:j2objc-annotations:1.3",
        "com.google.truth:truth:1.1.3",
        "com.squareup.okhttp:okhttp:2.7.5",
        "io.netty:netty-buffer:4.1.70.Final",
        "io.netty:netty-codec-http2:4.1.70.Final",
        "io.netty:netty-codec-http:4.1.70.Final",
        "io.netty:netty-codec-socks:4.1.70.Final",
        "io.netty:netty-codec:4.1.70.Final",
        "io.netty:netty-common:4.1.70.Final",
        "io.netty:netty-handler-proxy:4.1.70.Final",
        "io.netty:netty-handler:4.1.70.Final",
        "io.netty:netty-resolver:4.1.70.Final",
        "io.netty:netty-tcnative-boringssl-static:2.0.46.Final",
        "io.netty:netty-transport-native-epoll:jar:linux-x86_64:4.1.70.Final",
        "io.netty:netty-transport:4.1.70.Final",
        "io.opencensus:opencensus-api:0.28.3",
        "io.opencensus:opencensus-contrib-grpc-metrics:0.28.3",
        "io.perfmark:perfmark-api:0.24.0",
        "org.apache.tomcat:annotations-api:6.0.53",
        "org.codehaus.mojo:animal-sniffer-annotations:1.20",
    ],
    fail_if_repin_required = False,
    fetch_javadoc = True,
    fetch_sources = True,
    generate_compat_repositories = True,
    maven_install_json = "//:maven_install.json",
    repositories = [
        "https://repo1.maven.org/maven2",
    ],
    version_conflict_policy = "pinned",
)

load("@maven//:defs.bzl", "pinned_maven_install")

pinned_maven_install()

load("@maven//:compat.bzl", "compat_repositories")

compat_repositories()

git_repository(
    name = "io_bazel_rules_docker",
    commit = "af1743d5e3b946930fcdcde3b8563ba3598ff3bd",
    remote = "https://github.com/jracollins/rules_docker.git",
    shallow_since = "1638195629 +0000",
)
