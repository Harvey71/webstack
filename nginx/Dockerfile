FROM nginx:1.17

COPY acme.sh /root/

WORKDIR /root/

RUN apt-get -qq update && \
    apt-get -qq install --yes ca-certificates curl openssl >/dev/null && \
    apt-get clean autoclean && \
    apt-get autoremove --yes && \
    rm -rf /var/lib/{apt,dpkg,cache,log} && \
    /root/acme.sh --install --force

VOLUME /etc/nginx
VOLUME /logs
VOLUME /html
VOLUME /ssl
