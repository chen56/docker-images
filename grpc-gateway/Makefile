all: build

.PHONY: build
build:
	docker build -t chen56/grpc-gateway:1.0 .
	docker tag chen56/grpc-gateway:1.0 chen56/grpc-gateway:latest

.PHONY: push
push:
	docker push chen56/grpc-gateway:1.0	
	docker push chen56/grpc-gateway:latest