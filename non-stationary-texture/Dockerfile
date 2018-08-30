FROM nvidia/cuda:8.0-cudnn7-devel-ubuntu16.04

MAINTAINER kamino410 <kamino.dev@gmail.com>

WORKDIR /root

RUN apt update && \
    apt install -y python2.7 python-pip git wget vim && \
    python -m pip install html visdom dominate && \
    python -m pip install http://download.pytorch.org/whl/cu80/torch-0.3.0-cp27-cp27mu-linux_x86_64.whl && \
    python -m pip install torchvision

RUN git clone https://github.com/jessemelpolio/non-stationary_texture_syn.git && \
    mkdir /root/non-stationary_texture_syn/Models && \
    cd /root/non-stationary_texture_syn/Models && \
    wget -c --no-check-certificate https://bethgelab.org/media/uploads/pytorch_models/vgg_conv.pth && \
    wget https://s3.amazonaws.com/download.onnx/models/opset_8/vgg19.tar.gz && \
    tar -xf vgg19.tar.gz

ENTRYPOINT bash

