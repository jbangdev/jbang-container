# Generated with JReleaser 1.19.0 at 2025-12-13T19:48:32.339123Z
FROM eclipse-temurin:21

LABEL "org.opencontainers.image.title"="jbang-java-21"
LABEL "org.opencontainers.image.description"="Unleash the power of Java"
LABEL "org.opencontainers.image.url"="https://jbang.dev"
LABEL "org.opencontainers.image.licenses"="MIT"
LABEL "org.opencontainers.image.version"="0.135.1"
LABEL "org.opencontainers.image.revision"="ac71400a123f3e460e14e98c97ba873d678035cb"
LABEL org.opencontainers.image.source=https://github.com/jbangdev/jbang-container


COPY assembly/ /

## mkdir of .userPrefs is to fix https://github.com/jbangdev/jbang/issues/1831
RUN jar xf jbang-0.135.1.zip && \
    rm jbang-0.135.1.zip && \
    chmod +x jbang-0.135.1/bin/jbang && \
    mkdir -p $HOME/.java/.userPrefs

    

VOLUME /workspace
ADD ./entrypoint /bin/entrypoint

ENV PATH="${PATH}:/jbang-0.135.1/bin"

ENTRYPOINT ["entrypoint"]
