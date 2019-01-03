
FROM ubuntu:16.04

RUN apt-get update && apt-get install -y \
  git \
  language-pack-ja-base \
  language-pack-ja \  
  python3.5 \
  python3-pip \
  python3-dev

RUN pip3 install --upgrade pip

COPY ./requirements.txt /requirements.txt
RUN pip install -r /requirements.txt

ARG UID
RUN useradd docker -l -u $UID -s /bin/bash -m
USER docker

WORKDIR /work

ENV LANG=ja_JP.UTF-8
ENV LC_ALL=C.UTF-8

ENTRYPOINT ["/bin/bash"]
