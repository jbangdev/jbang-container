# Generated with JReleaser 1.19.0 at 2025-07-31T05:36:18.993779Z
FROM eclipse-temurin:21

LABEL "org.opencontainers.image.title"="jbang-java-21"
LABEL "org.opencontainers.image.description"="Unleash the power of Java"
LABEL "org.opencontainers.image.url"="https://jbang.dev"
LABEL "org.opencontainers.image.licenses"="MIT"
LABEL "org.opencontainers.image.version"="0.128.7"
LABEL "org.opencontainers.image.revision"="78020cbf1b52e81280ddd1ba0e87c07dd5c11490"
LABEL org.opencontainers.image.source=https://github.com/jbangdev/jbang-container


COPY assembly/ /

## mkdir of .userPrefs is to fix https://github.com/jbangdev/jbang/issues/1831
RUN jar xf jbang-0.128.7.zip && \
    rm jbang-0.128.7.zip && \
    chmod +x jbang-0.128.7/bin/jbang && \
    mkdir -p $HOME/.java/.userPrefs

    

VOLUME /workspace
ADD ./entrypoint /bin/entrypoint

ENV PATH="${PATH}:/jbang-0.128.7/bin"

ENTRYPOINT ["entrypoint"]
