FROM alpine:3.17
LABEL maintainer="ProcessOne <contact@process-one.net>" \
      product="Ejabberd mix development environment"

# 加速
RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories

# Install required dependencies
RUN apk upgrade --update musl \
    && apk add build-base git zlib-dev openssl openssl-dev yaml-dev expat-dev sqlite-dev \
    gd-dev jpeg-dev libpng-dev libwebp-dev autoconf automake bash \
    elixir erlang-reltool erlang-odbc file curl \
    && rm -rf /var/cache/apk/*

# Setup runtime environment
RUN mix local.hex --force \
    && mix local.rebar --force

ENTRYPOINT ["/usr/bin/mix"]
CMD ["compile"]
