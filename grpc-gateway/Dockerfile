# Dockerfile for gRPC Go
FROM golang:1.12rc1

# docker run --rm -it chen56/grpc-gateway:latest sh

RUN set -x && \
    apt-get update && \
    apt-get -y install unzip && \
    apt-get clean 

## protoc
RUN curl -L https://github.com/protocolbuffers/protobuf/releases/download/v3.6.1/protoc-3.6.1-linux-x86_64.zip > /tmp/protoc.zip && \
    unzip -d /tmp/protoc/ /tmp/protoc.zip && \
    cp /tmp/protoc/bin/protoc /usr/local/bin && \
    cp -R /tmp/protoc/include/* /usr/local/include && \
    rm -r /tmp/* 

## grpc-gateway
RUN go get -u github.com/grpc-ecosystem/grpc-gateway/protoc-gen-grpc-gateway && \
    go get -u github.com/grpc-ecosystem/grpc-gateway/protoc-gen-swagger && \
    go get -u github.com/golang/protobuf/protoc-gen-go && \
    cd /go/src/github.com/golang/protobuf/proto && \
    git checkout tags/v1.2.0 -b v1.2.0 && \
    go install

# Install swagger-codegen
ENV SWAGGER_CODEGEN_VERSION=2.4.1
RUN apt-get install -y openjdk-8-jre wget && \
    wget http://repo1.maven.org/maven2/io/swagger/swagger-codegen-cli/${SWAGGER_CODEGEN_VERSION}/swagger-codegen-cli-${SWAGGER_CODEGEN_VERSION}.jar \
    -O /usr/local/bin/swagger-codegen-cli.jar && \
    apt-get remove -y wget
ENV SWAGGER_CODEGEN="java -jar /usr/local/bin/swagger-codegen-cli.jar"

# Install swagger-codegen
ENV SWAGGER3_CODEGEN_VERSION=3.0.4
RUN apt-get install -y openjdk-8-jre wget && \
    wget http://repo1.maven.org/maven2/io/swagger/codegen/v3/swagger-codegen-cli/${SWAGGER3_CODEGEN_VERSION}/swagger-codegen-cli-${SWAGGER3_CODEGEN_VERSION}.jar \
    -O /usr/local/bin/swagger3-codegen-cli.jar && \
    apt-get remove -y wget
ENV SWAGGER3_CODEGEN="java -jar /usr/local/bin/swagger3-codegen-cli.jar"
