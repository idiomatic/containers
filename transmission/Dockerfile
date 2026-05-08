FROM docker.io/library/alpine:latest

RUN set -eux && \
    apk --no-cache add --repository=https://dl-cdn.alpinelinux.org/alpine/edge/community transmission-daemon transmission-remote transmission-extra

ENTRYPOINT ["/usr/bin/transmission-daemon", "--foreground", "--config-dir", "/config"]

EXPOSE 9091

VOLUME /config
VOLUME /downloads
VOLUME /watch
