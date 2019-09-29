ARG baseimage=arm32v7/node:dubnium-buster
FROM ${baseimage}

# apt mirror
RUN sed -i s/deb.debian.org/mirrors.tuna.tsinghua.edu.cn/g /etc/apt/sources.list

RUN apt-get update && apt-get install -y --no-install-recommends build-essential libsecret-1-dev fakeroot rpm libx11-dev libxkbfile-dev git libgtk-3-dev libxss-dev libasound2-dev && rm -rf /var/lib/apt/list/*

# mirror/proxy for build environment 
ENV ELECTRON_MIRROR="https://mirrors.huaweicloud.com/electron/"

# https proxy
ENV https_proxy="http://192.168.1.22:4411"

