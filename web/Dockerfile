FROM nginx:1.15.2-alpine

ARG AGENT_UID=1000
RUN adduser -D -H -s /bin/sh -u ${AGENT_UID} appagent

ENV CONF_PATH /etc/nginx/conf.d

COPY default.conf $CONF_PATH
COPY nginx.conf /etc/nginx/nginx.conf