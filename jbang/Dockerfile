# Generated with JReleaser 1.19.0 at 2025-11-27T08:26:27.286372Z
FROM eclipse-temurin:21

LABEL "org.opencontainers.image.title"="jbang-java-21"
LABEL "org.opencontainers.image.description"="Unleash the power of Java"
LABEL "org.opencontainers.image.url"="https://jbang.dev"
LABEL "org.opencontainers.image.licenses"="MIT"
LABEL "org.opencontainers.image.version"="0.134.3"
LABEL "org.opencontainers.image.revision"="f1613d0c9750062cfba6c4926d099a9a993f3253"
LABEL org.opencontainers.image.source=https://github.com/jbangdev/jbang-container


COPY assembly/ /

## mkdir of .userPrefs is to fix https://github.com/jbangdev/jbang/issues/1831
RUN jar xf jbang-0.134.3.zip && \
    rm jbang-0.134.3.zip && \
    chmod +x jbang-0.134.3/bin/jbang && \
    mkdir -p $HOME/.java/.userPrefs

    

VOLUME /workspace
ADD ./entrypoint /bin/entrypoint

ENV PATH="${PATH}:/jbang-0.134.3/bin"

ENTRYPOINT ["entrypoint"]
