FROM ubuntu:18.04

MAINTAINER kamino410 <kamino.dev@gmail.com>

WORKDIR /root

RUN apt update && \
    apt install -y build-essential cmake git libgtk2.0-dev pkg-config libavcodec-dev libavformat-dev libswscale-dev
RUN git clone https://github.com/opencv/opencv.git && \
    cd opencv && \
    git checkout refs/tags/4.0.0 && \
    mkdir build && cd build && \
    cmake -D CMAKE_BUILD_TYPE=Debug -D CMAKE_INSTALL_PREFIX=/usr .. && \
    make -j7 && \
    make install

ENTRYPOINT bash

