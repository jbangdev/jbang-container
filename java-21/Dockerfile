# Generated with JReleaser 1.27.0-SNAPSHOT at 2026-10-30T22:08:58.327658404Z
FROM eclipse-temurin:21

LABEL "org.opencontainers.image.title"="jbang-java-21"
LABEL "org.opencontainers.image.description"="Unleash the power of Java"
LABEL "org.opencontainers.image.url"="https://jbang.dev"
LABEL "org.opencontainers.image.licenses"="MIT"
LABEL "org.opencontainers.image.version"="0.143.0"
LABEL "org.opencontainers.image.revision"="b63ca593dfed3e92f8c704d7b5a271a9cd108ffa"
LABEL "org.opencontainers.image.source"="https://github.com/jbangdev/jbang-container"
LABEL org.opencontainers.image.source=https://github.com/jbangdev/jbang-container


COPY assembly/ /

## mkdir of .userPrefs is to fix https://github.com/jbangdev/jbang/issues/1831
RUN jar xf jbang-0.143.0.zip && \
    rm jbang-0.143.0.zip && \
    chmod +x jbang-0.143.0/bin/jbang && \
    mkdir -p $HOME/.java/.userPrefs

    

VOLUME /workspace
ADD ./entrypoint /bin/entrypoint

ENV PATH="${PATH}:/jbang-0.143.0/bin"

ENTRYPOINT ["entrypoint"]
