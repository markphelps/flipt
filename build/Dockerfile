# https://goreleaser.com/docker/

ARG BINARY=flipt
ARG ALPINE_VERSION=3.10.9

FROM alpine:${ALPINE_VERSION}
LABEL maintainer="mark.aaron.phelps@gmail.com"
LABEL org.opencontainers.image.name="flipt"
LABEL org.opencontainers.image.source="https://github.com/markphelps/flipt"

RUN apk add --no-cache postgresql-client \
    openssl \
    ca-certificates

RUN mkdir -p /etc/flipt && \
    mkdir -p /var/opt/flipt

COPY $BINARY /
COPY config/migrations/ /etc/flipt/config/migrations/
COPY config/*.yml /etc/flipt/config/

EXPOSE 8080
EXPOSE 9000

CMD ["./flipt"]
