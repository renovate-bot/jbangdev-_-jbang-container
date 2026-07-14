# Generated with JReleaser 1.25.0-SNAPSHOT at 2026-07-14T05:08:56.758974619Z
FROM eclipse-temurin:17

LABEL "org.opencontainers.image.title"="jbang-java-17"
LABEL "org.opencontainers.image.description"="Unleash the power of Java"
LABEL "org.opencontainers.image.url"="https://jbang.dev"
LABEL "org.opencontainers.image.licenses"="MIT"
LABEL "org.opencontainers.image.version"="0.141.0"
LABEL "org.opencontainers.image.revision"="d56044dd5ff151aca4cf42a719af8a3dbd29cdf7"
LABEL "org.opencontainers.image.source"="https://github.com/jbangdev/jbang-container"
LABEL org.opencontainers.image.source=https://github.com/jbangdev/jbang-container


COPY assembly/ /

## mkdir of .userPrefs is to fix https://github.com/jbangdev/jbang/issues/1831
RUN jar xf jbang-0.141.0.zip && \
    rm jbang-0.141.0.zip && \
    chmod +x jbang-0.141.0/bin/jbang && \
    mkdir -p $HOME/.java/.userPrefs

    

VOLUME /workspace
ADD ./entrypoint /bin/entrypoint

ENV PATH="${PATH}:/jbang-0.141.0/bin"

ENTRYPOINT ["entrypoint"]
