#利用するUbuntuのイメージ
FROM ubuntu:latest

# タイムゾーン
RUN ln -sf /usr/share/zoneinfo/Asia/Tokyo /etc/localtime

# install python and pip

RUN apt update
RUN apt install --no-install-recommends -y python3 \
                python3-pip \
                python3-dev \
                python3-venv \
                python3-wheel \
                build-essential \
                libopencv-dev \
                git

RUN apt install -y vim

RUN pip install --upgrade pip
RUN pip install opencv-python ipykernel kwcoco matplotlib

RUN ln -sv /usr/bin/python3 /usr/bin/python
