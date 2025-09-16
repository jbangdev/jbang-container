# Generated with JReleaser 1.19.0 at 2025-09-16T20:34:55.787692Z
FROM eclipse-temurin:21

LABEL "org.opencontainers.image.title"="jbang-java-21"
LABEL "org.opencontainers.image.description"="Unleash the power of Java"
LABEL "org.opencontainers.image.url"="https://jbang.dev"
LABEL "org.opencontainers.image.licenses"="MIT"
LABEL "org.opencontainers.image.version"="0.131.0"
LABEL "org.opencontainers.image.revision"="776fac4861e5e3644509e311f1bc7d5c4f8d61af"
LABEL org.opencontainers.image.source=https://github.com/jbangdev/jbang-container


COPY assembly/ /

## mkdir of .userPrefs is to fix https://github.com/jbangdev/jbang/issues/1831
RUN jar xf jbang-0.131.0.zip && \
    rm jbang-0.131.0.zip && \
    chmod +x jbang-0.131.0/bin/jbang && \
    mkdir -p $HOME/.java/.userPrefs

    

VOLUME /workspace
ADD ./entrypoint /bin/entrypoint

ENV PATH="${PATH}:/jbang-0.131.0/bin"

ENTRYPOINT ["entrypoint"]
