# Generated with JReleaser 1.19.0 at 2026-02-03T18:23:53.933137Z
FROM eclipse-temurin:21

LABEL "org.opencontainers.image.title"="jbang-java-21"
LABEL "org.opencontainers.image.description"="Unleash the power of Java"
LABEL "org.opencontainers.image.url"="https://jbang.dev"
LABEL "org.opencontainers.image.licenses"="MIT"
LABEL "org.opencontainers.image.version"="0.136.0"
LABEL "org.opencontainers.image.revision"="4bcb11945c968cdcb9b1f8a75f246dbc4d00633b"
LABEL org.opencontainers.image.source=https://github.com/jbangdev/jbang-container


COPY assembly/ /

## mkdir of .userPrefs is to fix https://github.com/jbangdev/jbang/issues/1831
RUN jar xf jbang-0.136.0.zip && \
    rm jbang-0.136.0.zip && \
    chmod +x jbang-0.136.0/bin/jbang && \
    mkdir -p $HOME/.java/.userPrefs

    

VOLUME /workspace
ADD ./entrypoint /bin/entrypoint

ENV PATH="${PATH}:/jbang-0.136.0/bin"

ENTRYPOINT ["entrypoint"]
