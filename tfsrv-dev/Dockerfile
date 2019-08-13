FROM ubuntu:18.04

WORKDIR /root
ENV DEBIAN_FRONTEND noninteractive

COPY extra-sources.list /etc/apt/
RUN cat /etc/apt/sources.list >> /etc/apt/extra-sources.list
RUN mv /etc/apt/extra-sources.list /etc/apt/sources.list

# Update source
RUN apt-get update -y
RUN apt-get upgrade -y

# Basic tools
RUN apt-get install -y --no-install-recommends \
    apt-utils

RUN apt-get install -y --no-install-recommends \
    pkg-config \
    unzip \
    zip \
    bsdmainutils \
    locales \
    vim

RUN apt-get install -y --no-install-recommends \
    rsync \
    openssh-server \
    curl \
    wget \
    telnet \
    net-tools \
    inetutils-ping \
    screen \
    htop

RUN apt-get install -y --no-install-recommends \
    git \
    build-essential \
    cmake \
    ccache

RUN apt-get install -y --no-install-recommends \
    libgoogle-glog-dev \
    libprotobuf-dev \
    protobuf-compiler \
    libprotoc-dev

RUN apt-get install -y --no-install-recommends \
    openjdk-8-jdk \
    openjdk-8-jre-headless

RUN locale-gen en_US.UTF-8
ENV LC_CTYPE=en_US.UTF-8
ENV LC_ALL=en_US.UTF-8
ENV TERM xterm-256color

# Customize vim
RUN git clone --recursive https://github.com/llhe/vimrc.git && \
    cd vimrc && \
    rm -rf ~/.vim && \
    rm -rf ~/.vimrc && \
    ln -s `pwd`/vim ~/.vim && \
    ln -s `pwd`/vimrc ~/.vimrc
