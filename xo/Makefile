export IMAGE_TAG  = 1.0

all: build

build:
	docker build --build-arg "http_proxy=$(http_proxy)" --build-arg "https_proxy=$(https_proxy)" -t chen56/xo:$(IMAGE_TAG) -t chen56/xo:latest .

push:
	docker push chen56/xo:$(IMAGE_TAG)
	docker push chen56/xo:latest