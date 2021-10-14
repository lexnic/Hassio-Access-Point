ARG BUILD_FROM
FROM $BUILD_FROM

RUN rm -rf /var/cache/apk/* && \
    rm -rf /tmp/*

RUN apk update && \
apk add --no-cache bash jq iw hostapd networkmanager net-tools sudo dnsmasq && \
rm -rf /var/cache/apk/*

MAINTAINER Denis Khurbatov <git@khurbd.com>

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

ENV LANG C.UTF-8

COPY hostapd.conf /
COPY dnsmasq.conf /

COPY run.sh /
RUN chmod a+x /run.sh

CMD [ "/run.sh" ]