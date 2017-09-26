#
# mo
#
FROM alpine:3.6
LABEL maintainer="chenpeng<chen56@msn.com>"

USER root

RUN set -xe \
    && echo "https://mirrors.tuna.tsinghua.edu.cn/alpine/v3.6/main" > /etc/apk/repositories \
    && echo "https://mirrors.tuna.tsinghua.edu.cn/alpine/v3.6/community" >> /etc/apk/repositories \
    && apk update \
    && apk add bash curl \
    && curl -sSL https://raw.githubusercontent.com/tests-always-included/mo/master/mo > /usr/local/bin/mo \
    && chmod +x /usr/local/bin/mo 

VOLUME /app

ENTRYPOINT ["mo"]

CMD ["--help"]