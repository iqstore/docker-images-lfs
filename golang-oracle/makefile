GO_VERSION = 1.16
ORACLE_VERSION = 12.2
TAG = docker.iqstore.ru/golang-oracle:${GO_VERSION}-${ORACLE_VERSION}

build:
	docker build -t $(TAG) .

push:
	docker push $(TAG)
