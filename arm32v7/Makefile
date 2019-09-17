builder:
	docker build -t atom-builder .

deb:
	docker run -t --rm -v ${CURDIR}/..:/atom -w '/atom/script' atom-builder sh -c "./bootstrap && ./build --create-debian-package"

clean:
	docker run -t --rm -v ${CURDIR}/..:/atom -w '/atom/script' atom-builder sh -c "mv package* /tmp && npm i fs-extra && ./clean && mv /tmp/package* ."

.PHONY: builder deb clean
