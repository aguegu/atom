ARG baseimage=arm32v7/node:dubnium-buster
FROM ${baseimage}

RUN apt-get update && apt-get install -y --no-install-recommends build-essential libsecret-1-dev fakeroot rpm libx11-dev libxkbfile-dev git libgtk-3-dev libxss-dev libasound2-dev && rm -rf /var/lib/apt/list/*

ENV ELECTRON_MIRROR="https://mirrors.huaweicloud.com/electron/"
ENV http_proxy="http://192.168.1.22:4411"
ENV https_proxy="http://192.168.1.22:4411"

