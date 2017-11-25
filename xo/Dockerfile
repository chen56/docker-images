#
# mo
#
FROM golang

LABEL maintainer="ChenPeng<chen56@msn.com>"

USER root

RUN set -eux; \
  go get -v -u golang.org/x/tools/cmd/goimports; \
  go get -v -u github.com/knq/xo;

ENTRYPOINT ["xo"]
