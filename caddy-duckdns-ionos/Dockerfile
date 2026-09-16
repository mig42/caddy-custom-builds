# syntax=docker.io/docker/dockerfile:1
ARG CADDY_VERSION

FROM caddy:${CADDY_VERSION}-builder AS builder

RUN xcaddy build \
    --with github.com/caddy-dns/duckdns

RUN xcaddy build \
    --with github.com/caddy-dns/ionos

FROM caddy:${CADDY_VERSION}

COPY --from=builder /usr/bin/caddy /usr/bin/caddy
