FROM php:7.1.9-fpm-alpine

COPY www.conf /usr/local/etc/php-fpm.d/zzz-www.conf

ARG AGENT_UID=1000
RUN adduser -D -H -s /bin/sh -u ${AGENT_UID} appagent
RUN mkdir -p /var/run/php-fpm \
  && chown appagent:appagent /var/run/php-fpm
