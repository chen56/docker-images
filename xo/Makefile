all: build

build:
	docker build --build-arg "http_proxy=$(http_proxy)" --build-arg "https_proxy=$(https_proxy)" -t chen56/xo .
push:
	docker push chen56/xo

