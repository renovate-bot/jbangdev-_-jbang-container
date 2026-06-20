# Generated with JReleaser 1.25.0-SNAPSHOT at 2026-06-20T17:19:51.359547368Z
FROM eclipse-temurin:8

LABEL "org.opencontainers.image.title"="jbang-java-8"
LABEL "org.opencontainers.image.description"="Unleash the power of Java"
LABEL "org.opencontainers.image.url"="https://jbang.dev"
LABEL "org.opencontainers.image.licenses"="MIT"
LABEL "org.opencontainers.image.version"="0.139.3"
LABEL "org.opencontainers.image.revision"="840d5468fe657f0f85e8fdb7d87b7b477a5bef5b"
LABEL "org.opencontainers.image.source"="https://github.com/jbangdev/jbang-container"
LABEL org.opencontainers.image.source=https://github.com/jbangdev/jbang-container


COPY assembly/ /

## mkdir of .userPrefs is to fix https://github.com/jbangdev/jbang/issues/1831
RUN jar xf jbang-0.139.3.zip && \
    rm jbang-0.139.3.zip && \
    chmod +x jbang-0.139.3/bin/jbang && \
    mkdir -p $HOME/.java/.userPrefs

    

VOLUME /workspace
ADD ./entrypoint /bin/entrypoint

ENV PATH="${PATH}:/jbang-0.139.3/bin"

ENTRYPOINT ["entrypoint"]
