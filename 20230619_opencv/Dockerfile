#利用するUbuntuのイメージ
FROM ubuntu:latest

# タイムゾーン
RUN ln -sf /usr/share/zoneinfo/Asia/Tokyo /etc/localtime

ARG PYTHON="3.9"
RUN apt update
RUN apt-get install --no-install-recommends -y  python${PYTHON} \
                                                python3-pip \
                                                git \
                                                libopencv-dev 

RUN apt-get autoremove -y
RUN pip install --upgrade pip

RUN ln -sv /usr/bin/python3 /usr/bin/python

# install opencv
RUN pip install opencv-python