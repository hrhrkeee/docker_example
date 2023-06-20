#利用するUbuntuのイメージ
FROM ubuntu:latest

ARG PYTHON="3.9"
RUN apt update
RUN apt-get install --no-install-recommends -y python${PYTHON}
RUN apt install -y python3-pip

RUN ln -sv /usr/bin/python3 /usr/bin/python

# aptインストール
# RUN apt update && \
#     apt install -y wget \
#                    git \
#                    curl \
#     rm -rf /var/lib/apt/lists


# ARG PYTHON="3.9"

# #利用するUbuntuのイメージ
# FROM ubuntu:latest




# USER root

# # 必要そうなものをinstall
# RUN apt-get update && apt-get install -y --no-install-recommends wget build-essential libreadline-dev \ 
# libncursesw5-dev libssl-dev libsqlite3-dev libgdbm-dev libbz2-dev liblzma-dev zlib1g-dev uuid-dev libffi-dev libdb-dev

# #任意バージョンのpythonをinstall
# RUN wget --no-check-certificate https://www.python.org/ftp/python/${PYTHON}/Python-${PYTHON}.tgz \
# && tar -xf Python-${PYTHON}.tgz \
# && cd Python-${PYTHON} \
# && ./configure --enable-optimizations\
# && make \
# && make install

# #サイズ削減のため不要なものは削除
# RUN apt-get autoremove -y

# #必要なpythonパッケージをpipでインストール
# #RUN pip3 install --upgrade pip && pip3 install --no-cache-dir jupyterlab

# #requirements.txtなら以下のように
# #RUN pip3 install -r ./requirements.txt

# RUN ln -sv /usr/bin/python3 /usr/bin/python