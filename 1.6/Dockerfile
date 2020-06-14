FROM eclipse-mosquitto:1.6.10

ARG BUILD_DATE
ARG VCS_REF

LABEL maintainer="Gabriele Besta <48332305+bg-master@users.noreply.github.com>" \
    org.opencontainers.image.created=$BUILD_DATE \
    org.opencontainers.image.authors="Gabriele Besta <48332305+bg-master@users.noreply.github.com>" \
    org.opencontainers.image.url="https://hub.docker.com/repository/docker/bgdevit/eclipse-mosquitto" \
    org.opencontainers.image.documentation="https://github.com/bgdev-it/docker-eclipse-mosquitto" \
    org.opencontainers.image.source="https://github.com/bgdev-it/docker-eclipse-mosquitto" \
    org.opencontainers.image.version="1.6.10" \
    org.opencontainers.image.revision=$VCS_REF \
    org.opencontainers.image.vendor="BGdev.it" \
    org.opencontainers.image.licenses="MIT" \
    org.opencontainers.image.title="eclipse-mosquittto" \
    org.opencontainers.image.description="Eclipse Mosquitto MQTT Broker"

COPY config /mosquitto/config

RUN set -x && \
    chmod 644 /mosquitto/config/mosquitto.conf && \
    apk --no-cache add tzdata && \
    rm -f /var/cache/apk/*

VOLUME ["/mosquitto/data", "/mosquitto/config", "/mosquitto/log"]

EXPOSE 1883

CMD ["/usr/sbin/mosquitto", "-c", "/mosquitto/config/mosquitto.conf"]
