builder:
	docker build -t atom-builder .

deb:
	docker run -t --rm -v ${CURDIR}/..:/atom -w '/atom/script' atom-builder sh -c "npm install electron-mksnapshot@4.2.0 && ./bootstrap"

.PHONY: builder
