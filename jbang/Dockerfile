# Generated with JReleaser 1.19.0 at 2025-07-27T12:10:57.123427Z
FROM eclipse-temurin:21

LABEL "org.opencontainers.image.title"="jbang-java-21"
LABEL "org.opencontainers.image.description"="Unleash the power of Java"
LABEL "org.opencontainers.image.url"="https://jbang.dev"
LABEL "org.opencontainers.image.licenses"="MIT"
LABEL "org.opencontainers.image.version"="0.128.2"
LABEL "org.opencontainers.image.revision"="62d3cc5146c02ec0f20b0e39c1839055cc9e4c2f"
LABEL org.opencontainers.image.source=https://github.com/jbangdev/jbang-container


COPY assembly/ /

## mkdir of .userPrefs is to fix https://github.com/jbangdev/jbang/issues/1831
RUN jar xf jbang-0.128.2.zip && \
    rm jbang-0.128.2.zip && \
    chmod +x jbang-0.128.2/bin/jbang && \
    mkdir -p $HOME/.java/.userPrefs

    

VOLUME /workspace
ADD ./entrypoint /bin/entrypoint

ENV PATH="${PATH}:/jbang-0.128.2/bin"

ENTRYPOINT ["entrypoint"]
