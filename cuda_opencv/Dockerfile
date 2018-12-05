FROM nvidia/cuda:10.0-devel-ubuntu18.04

MAINTAINER kamino410 <kamino.dev@gmail.com>

WORKDIR /root

RUN apt update && \
    apt install -y build-essential cmake git libgtk2.0-dev pkg-config libavcodec-dev libavformat-dev libswscale-dev
RUN git clone https://github.com/opencv/opencv.git && \
    git clone https://github.com/opencv/opencv_contrib.git && \
    cd opencv_contrib  && \
    git checkout refs/tags/4.0.0 && \
    cd ../opencv && \
    git checkout refs/tags/4.0.0 && \
    mkdir build && cd build && \
    cmake -D CMAKE_BUILD_TYPE=Release -D CMAKE_INSTALL_PREFIX=/usr -D OPENCV_EXTRA_MODULES_PATH=../../opencv_contrib/modules .. && \
    make -j7 && \
    make install

ENTRYPOINT bash
