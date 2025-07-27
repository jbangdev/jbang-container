# Generated with JReleaser 1.19.0 at 2025-07-27T13:49:26.465518Z
FROM eclipse-temurin:21

LABEL "org.opencontainers.image.title"="jbang-java-21"
LABEL "org.opencontainers.image.description"="Unleash the power of Java"
LABEL "org.opencontainers.image.url"="https://jbang.dev"
LABEL "org.opencontainers.image.licenses"="MIT"
LABEL "org.opencontainers.image.version"="0.128.5"
LABEL "org.opencontainers.image.revision"="915e09dd96062609a4cab07e37d72bf478db7a95"
LABEL org.opencontainers.image.source=https://github.com/jbangdev/jbang-container


COPY assembly/ /

## mkdir of .userPrefs is to fix https://github.com/jbangdev/jbang/issues/1831
RUN jar xf jbang-0.128.5.zip && \
    rm jbang-0.128.5.zip && \
    chmod +x jbang-0.128.5/bin/jbang && \
    mkdir -p $HOME/.java/.userPrefs

    

VOLUME /workspace
ADD ./entrypoint /bin/entrypoint

ENV PATH="${PATH}:/jbang-0.128.5/bin"

ENTRYPOINT ["entrypoint"]
