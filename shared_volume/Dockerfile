FROM alpine:3.8

RUN apk --update add git openssh && \
    rm -rf /var/lib/apt/lists/* && \
    rm /var/cache/apk/*

# nginx - php-fpm用のソケットファイルディレクトリ
ARG AGENT_UID=1000
RUN adduser -D -H -s /bin/sh -u ${AGENT_UID} appagent
RUN mkdir -p /var/run/php-fpm \
  && chown appagent:appagent /var/run/php-fpm

# プログラムソース
ENV SRC_ROOT /src
RUN mkdir -p $SRC_ROOT
WORKDIR $SRC_ROOT
RUN git clone https://github.com/D-Suzuki/phalcon-game-api.git api
