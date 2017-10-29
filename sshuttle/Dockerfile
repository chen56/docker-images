#
# mo
#
FROM python:2-alpine3.6

LABEL maintainer="ChenPeng<chen56@msn.com>"

USER root

RUN set -xe \
    && echo "https://mirrors.tuna.tsinghua.edu.cn/alpine/v3.6/main" > /etc/apk/repositories \
    && echo "https://mirrors.tuna.tsinghua.edu.cn/alpine/v3.6/community" >> /etc/apk/repositories \
    && apk update \
    && apk add bash curl \
    && pip install sshuttle 

VOLUME /app

ENTRYPOINT ["sshuttle"]

CMD ["--help"]