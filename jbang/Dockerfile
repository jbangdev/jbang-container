# Generated with JReleaser 1.19.0 at 2025-11-30T15:50:53.256892Z
FROM eclipse-temurin:21

LABEL "org.opencontainers.image.title"="jbang-java-21"
LABEL "org.opencontainers.image.description"="Unleash the power of Java"
LABEL "org.opencontainers.image.url"="https://jbang.dev"
LABEL "org.opencontainers.image.licenses"="MIT"
LABEL "org.opencontainers.image.version"="0.135.0"
LABEL "org.opencontainers.image.revision"="f3c68b2de321d21a4c312e283e4a0cbc9cdc38cb"
LABEL org.opencontainers.image.source=https://github.com/jbangdev/jbang-container


COPY assembly/ /

## mkdir of .userPrefs is to fix https://github.com/jbangdev/jbang/issues/1831
RUN jar xf jbang-0.135.0.zip && \
    rm jbang-0.135.0.zip && \
    chmod +x jbang-0.135.0/bin/jbang && \
    mkdir -p $HOME/.java/.userPrefs

    

VOLUME /workspace
ADD ./entrypoint /bin/entrypoint

ENV PATH="${PATH}:/jbang-0.135.0/bin"

ENTRYPOINT ["entrypoint"]
