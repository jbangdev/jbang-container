# Generated with JReleaser 1.27.0-SNAPSHOT at 2026-09-22T17:25:42.996872228Z
FROM eclipse-temurin:21

LABEL "org.opencontainers.image.title"="jbang-java-21"
LABEL "org.opencontainers.image.description"="Unleash the power of Java"
LABEL "org.opencontainers.image.url"="https://jbang.dev"
LABEL "org.opencontainers.image.licenses"="MIT"
LABEL "org.opencontainers.image.version"="0.142.0"
LABEL "org.opencontainers.image.revision"="d98cbdf5814582ffdb99501f750a502f2c4fcd3c"
LABEL "org.opencontainers.image.source"="https://github.com/jbangdev/jbang-container"
LABEL org.opencontainers.image.source=https://github.com/jbangdev/jbang-container


COPY assembly/ /

## mkdir of .userPrefs is to fix https://github.com/jbangdev/jbang/issues/1831
RUN jar xf jbang-0.142.0.zip && \
    rm jbang-0.142.0.zip && \
    chmod +x jbang-0.142.0/bin/jbang && \
    mkdir -p $HOME/.java/.userPrefs

    

VOLUME /workspace
ADD ./entrypoint /bin/entrypoint

ENV PATH="${PATH}:/jbang-0.142.0/bin"

ENTRYPOINT ["entrypoint"]
