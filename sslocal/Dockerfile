FROM alpine:3.5
MAINTAINER "Xiao Mo" <root@xiaomo.red>

COPY repositories /etc/apk/repositories

RUN apk add --no-cache python py-pip python-dev pwgen \
    && pip install shadowsocks setuptools

COPY docker-entrypoint.sh /docker-entrypoint.sh

ENV PASSWORD **NULL**
ENV SERVER_METHOD aes-256-cfb
ENV SERVER_PORT 8388
ENV LOCAL_ADDR 127.0.0.1

EXPOSE 1080

CMD ["/docker-entrypoint.sh"]
