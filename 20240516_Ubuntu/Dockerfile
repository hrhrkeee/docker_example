FROM ubuntu:latest

RUN apt-get update && apt-get upgrade -y
RUN apt-get install -y sudo
RUN apt-get install -y wget
RUN apt-get install -y curl
RUN apt-get install -y nano

# NGINXのインストール
RUN apt-get install -y nginx
RUN echo "daemon off;" >> /etc/nginx/nginx.conf

RUN apt-get autoremove -y &&\
apt-get clean &&\
rm -rf /usr/local/src/*

# ユーザーの作成
# docker-compose.yamlより
ARG UBUNTU_GROUP_NAME
ARG UBUNTU_USER_NAME
ARG UBUNTU_USER_PASSWORD

ARG UID=1010
ARG GID=1010

RUN groupadd -g $GID ${UBUNTU_GROUP_NAME} && \
useradd -m -s /bin/bash -u $UID -g $GID -G sudo ${UBUNTU_USER_NAME} && \
echo ${UBUNTU_USER_NAME}:${UBUNTU_USER_PASSWORD} | chpasswd && \
echo "${UBUNTU_USER_NAME}   ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

# USER root
# CMD ["/usr/sbin/nginx", "-g", "daemon off;"]
# CMD ["/usr/sbin/nginx -g deamon off;"]

USER ${UBUNTU_USER_NAME}
WORKDIR /home/${UBUNTU_USER_NAME}/