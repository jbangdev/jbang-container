# Generated with JReleaser 1.19.0 at 2025-09-10T00:50:20.073419Z
FROM eclipse-temurin:21

LABEL "org.opencontainers.image.title"="jbang-java-21"
LABEL "org.opencontainers.image.description"="Unleash the power of Java"
LABEL "org.opencontainers.image.url"="https://jbang.dev"
LABEL "org.opencontainers.image.licenses"="MIT"
LABEL "org.opencontainers.image.version"="0.130.0"
LABEL "org.opencontainers.image.revision"="3f7757d031ca2d9075f991bda94a843378beb411"
LABEL org.opencontainers.image.source=https://github.com/jbangdev/jbang-container


COPY assembly/ /

## mkdir of .userPrefs is to fix https://github.com/jbangdev/jbang/issues/1831
RUN jar xf jbang-0.130.0.zip && \
    rm jbang-0.130.0.zip && \
    chmod +x jbang-0.130.0/bin/jbang && \
    mkdir -p $HOME/.java/.userPrefs

    

VOLUME /workspace
ADD ./entrypoint /bin/entrypoint

ENV PATH="${PATH}:/jbang-0.130.0/bin"

ENTRYPOINT ["entrypoint"]
