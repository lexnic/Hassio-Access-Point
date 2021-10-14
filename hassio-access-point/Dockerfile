ARG BUILD_FROM=ghcr.io/home-assistant/armv7-base:3.12
FROM $BUILD_FROM

RUN apk update && \
apk add --no-cache bash jq iw hostapd networkmanager net-tools sudo dnsmasq && \
rm -rf /var/cache/apk/*

MAINTAINER Denis Khurbatov <khurbd@gmail.com>

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

ENV LANG C.UTF-8

COPY hostapd.conf /
COPY dnsmasq.conf /

COPY run.sh /
RUN chmod a+x /run.sh

CMD [ "/run.sh" ]