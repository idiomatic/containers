FROM docker.io/library/alpine:latest
MAINTAINER Brian Harrison <containers@rbrian.com>

RUN set -eux && \
    apk --update --no-cache add avahi

RUN sed -ie 's/^#*enable-dbus=.*/enable-dbus=no/' /etc/avahi/avahi-daemon.conf

#COPY samba.service /etc/avahi/services/

ENTRYPOINT ["avahi-daemon", "--no-rlimits"]

VOLUME /etc/avahi/services
