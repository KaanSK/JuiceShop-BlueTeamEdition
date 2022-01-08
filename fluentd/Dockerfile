FROM fluent/fluentd:v1.14-1
LABEL maintainer="Kaan S. Karadag <kaansk@gmail.com>"

USER root

RUN apk add --no-cache --update --virtual .build-deps curl git \
        sudo build-base ruby-dev \
 && sudo gem install fluent-plugin-splunk-hec fluent-plugin-modsecurity \
 && sudo gem sources --clear-all \
 && apk del .build-deps \
 && rm -rf /tmp/* /var/tmp/* /usr/lib/ruby/gems/*/cache/*.gem