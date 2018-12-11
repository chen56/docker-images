# Dockerfile for gRPC Go
FROM golang:1.11

RUN set -x && \
    apt-get update && \
    apt-get -y install unzip && \
    apt-get clean && \
    ## protoc
    curl -L https://github.com/protocolbuffers/protobuf/releases/download/v3.6.1/protoc-3.6.1-linux-x86_64.zip > /tmp/protoc.zip && \
    unzip -d /tmp/protoc/ /tmp/protoc.zip && \
    cp /tmp/protoc/bin/protoc /usr/local/bin && \
    cp -R /tmp/protoc/include/* /usr/local/include && \
    rm -r /tmp/* && \
    ## grpc-gateway
    go get -u github.com/grpc-ecosystem/grpc-gateway/protoc-gen-grpc-gateway && \
    go get -u github.com/grpc-ecosystem/grpc-gateway/protoc-gen-swagger && \
    go get -u github.com/golang/protobuf/protoc-gen-go