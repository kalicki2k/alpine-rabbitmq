FROM kalicki2k/alpine-base:3.10

MAINTAINER Sebastian Kalicki (https://github.com/kalicki2k)

COPY Dockerfiles /

RUN echo http://dl-cdn.alpinelinux.org/alpine/edge/testing >> /etc/apk/repositories && \
    apk update && apk upgrade && \
    apk add rabbitmq-server && \
    adduser -DS -g "" -G rabbitmq -s /bin/sh -h /var/lib/rabbitmq rabbitmq && \
    mkdir -p /data/rabbitmq && \
    chown -R rabbitmq:rabbitmq /data/rabbitmq && \
    rm -rf /var/cache/apk/*

VOLUME ['/data/rabbitmq']

EXPOSE 5672/tcp 15672/tcp
