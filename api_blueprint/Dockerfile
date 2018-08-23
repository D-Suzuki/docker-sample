FROM node:8.11.4-alpine

RUN apk update \
 && apk --no-cache add \
    make \
    gcc \
    g++
RUN apk --no-cache add python

ENV APP_ROOT /usr/src/api_blueprint

RUN mkdir -p $APP_ROOT
RUN mkdir -p /usr/src/api_blueprint/src

WORKDIR $APP_ROOT

COPY *.json /usr/src/api_blueprint/
COPY gulpfile.js /usr/src/api_blueprint

RUN npm install -g gulp && npm install && npm install -g hariko --unsafe-perm && npm cache clean --force

CMD gulp && hariko -f 'src/apidocs/*.md' -v --host 0.0.0.0 --watch


