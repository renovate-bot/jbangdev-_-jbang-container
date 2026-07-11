# Generated with JReleaser 1.25.0-SNAPSHOT at 2026-07-11T16:25:54.661905162Z
FROM eclipse-temurin:17

LABEL "org.opencontainers.image.title"="jbang-java-17"
LABEL "org.opencontainers.image.description"="Unleash the power of Java"
LABEL "org.opencontainers.image.url"="https://jbang.dev"
LABEL "org.opencontainers.image.licenses"="MIT"
LABEL "org.opencontainers.image.version"="0.140.1"
LABEL "org.opencontainers.image.revision"="f633b04e5e3dd1c48eaa173191673f2e552b6c5b"
LABEL "org.opencontainers.image.source"="https://github.com/jbangdev/jbang-container"
LABEL org.opencontainers.image.source=https://github.com/jbangdev/jbang-container


COPY assembly/ /

## mkdir of .userPrefs is to fix https://github.com/jbangdev/jbang/issues/1831
RUN jar xf jbang-0.140.1.zip && \
    rm jbang-0.140.1.zip && \
    chmod +x jbang-0.140.1/bin/jbang && \
    mkdir -p $HOME/.java/.userPrefs

    

VOLUME /workspace
ADD ./entrypoint /bin/entrypoint

ENV PATH="${PATH}:/jbang-0.140.1/bin"

ENTRYPOINT ["entrypoint"]
