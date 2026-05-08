FROM docker.io/library/alpine:latest

ENV GID=1000

RUN set -eux && \
    apk --update --no-cache add samba && \
    addgroup -S -g $GID samba && \
    mkdir -m 1775 -p /usr/share/samba && \
    chgrp samba /usr/share/samba

EXPOSE 137/udp
EXPOSE 138/udp
EXPOSE 139
EXPOSE 445

# HEALTHCHECK ...

COPY smbaddusers smbdelusers /usr/bin/

ENTRYPOINT ["/usr/sbin/smbd", "--foreground", "--debug-stdout", "--debuglevel=1", "--no-process-group", "-F"]

VOLUME /etc/samba
VOLUME /var/lib/samba
