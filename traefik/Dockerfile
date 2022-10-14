FROM alpine
ARG PLUGIN_MODULE=github.com/acouvreur/traefik-modsecurity-plugin
ARG PLUGIN_GIT_REPO=https://github.com/acouvreur/traefik-modsecurity-plugin.git
ARG PLUGIN_GIT_BRANCH=main
RUN apk add --update git && \
    git clone ${PLUGIN_GIT_REPO} /plugins-local/src/${PLUGIN_MODULE} \
      --depth 1 --single-branch --branch ${PLUGIN_GIT_BRANCH}

FROM traefik:v2.5.6
COPY --from=0 /plugins-local /plugins-local