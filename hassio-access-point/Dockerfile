ARG BUILD_FROM=ghcr.io/home-assistant/armv7-base:3.14
FROM $BUILD_FROM

MAINTAINER Matt Longman <git@mattlongman.com>

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

ENV LANG C.UTF-8

RUN apk update && \
apk add --no-cache bash jq iw hostapd networkmanager net-tools sudo dnsmasq && \
rm -rf /var/cache/apk/*

COPY hostapd.conf /
COPY dnsmasq.conf /

COPY run.sh /
RUN chmod a+x /run.sh

CMD [ "/run.sh" ]