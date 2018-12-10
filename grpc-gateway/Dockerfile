# Dockerfile for gRPC Go
FROM grpc/go:1.0

# Install protoc-gen-go
# RUN go get -u github.com/grpc-ecosystem/grpc-gateway/protoc-gen-grpc-gateway && \
#     go get -u github.com/grpc-ecosystem/grpc-gateway/protoc-gen-swagger && \
#     go get -u github.com/golang/protobuf/protoc-gen-go

# Install grpc-gateway
RUN mkdir -p /tmp/grpc-gateway && \
    curl -L https://github.com/grpc-ecosystem/grpc-gateway/archive/v1.6.2.zip > /tmp/grpc-gateway/grpc-gateway.zip && \
    cd /tmp/grpc-gateway && \
    unzip grpc-gateway.zip && \
    mkdir -p /go/src/github.com/golang/grpc-gateway/protoc-gen-grpc-gateway/ && \
    cp -r /tmp/grpc-gateway/grpc-gateway-1.6.2/protoc-gen-grpc-gateway/* /go/src/github.com/golang/grpc-gateway/protoc-gen-grpc-gateway/ && \
    mkdir -p /go/src/github.com/golang/grpc-gateway/protoc-gen-swagger/ && \
    cp -r /tmp/grpc-gateway/grpc-gateway-1.6.2/protoc-gen-swagger/* /go/src/github.com/golang/grpc-gateway/protoc-gen-swagger/

