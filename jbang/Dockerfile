# Generated with JReleaser 1.19.0 at 2026-02-13T23:32:57.701708Z
FROM eclipse-temurin:21

LABEL "org.opencontainers.image.title"="jbang-java-21"
LABEL "org.opencontainers.image.description"="Unleash the power of Java"
LABEL "org.opencontainers.image.url"="https://jbang.dev"
LABEL "org.opencontainers.image.licenses"="MIT"
LABEL "org.opencontainers.image.version"="0.137.0"
LABEL "org.opencontainers.image.revision"="de43d9614ade9eb7ec2117ef3b380cea9240b5db"
LABEL org.opencontainers.image.source=https://github.com/jbangdev/jbang-container


COPY assembly/ /

## mkdir of .userPrefs is to fix https://github.com/jbangdev/jbang/issues/1831
RUN jar xf jbang-0.137.0.zip && \
    rm jbang-0.137.0.zip && \
    chmod +x jbang-0.137.0/bin/jbang && \
    mkdir -p $HOME/.java/.userPrefs

    

VOLUME /workspace
ADD ./entrypoint /bin/entrypoint

ENV PATH="${PATH}:/jbang-0.137.0/bin"

ENTRYPOINT ["entrypoint"]
