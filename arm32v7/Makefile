builder:
	docker build -t atom-builder .

deb:
	docker run -t --rm -v ${CURDIR}/..:/atom -w '/atom/script' atom-builder sh -c "./clean && npm install electron-download"

.PHONY: builder
