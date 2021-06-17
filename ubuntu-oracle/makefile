UBUNTU_VERSION = 20.04
ORACLE_VERSION = 12.2
TAG = docker.iqstore.ru/ubuntu-oracle:${UBUNTU_VERSION}-${ORACLE_VERSION}

build:
	docker build -t $(TAG) .

push:
	docker push $(TAG)
