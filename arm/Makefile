ARCHITECTURE := amd64
ARCH != uname -m

ifeq ($(ARCH), armv7l)
	ARCHITECTURE = arm32v7
else ifeq ($(ARCH), aarch64)
	ARCHITECTURE = arm64v8
endif

BASEIMAGE=${ARCHITECTURE}/node:dubnium-buster

builder:
	docker build -t atom-builder --build-arg baseimage=${BASEIMAGE} .

deps:
	docker run -t --rm -v ${CURDIR}/..:/atom -w '/atom/script' atom-builder sh -c "npm install"

deb:
	docker run -t --rm -v ${CURDIR}/..:/atom -w '/atom/script' atom-builder sh -c "./bootstrap && ./build --create-debian-package"

clean:
	docker run -t --rm -v ${CURDIR}/..:/atom -w '/atom/script' atom-builder sh -c "mv package* /tmp && npm i fs-extra && ./clean && mv /tmp/package* ."

.PHONY: builder deb clean
