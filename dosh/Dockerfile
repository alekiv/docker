FROM ubuntu:latest
MAINTAINER alekiv@gmail.com
ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update && apt-get install --no-install-recommends -y apt-utils locales && apt-get -y upgrade
RUN echo "en_US.UTF-8 UTF-8" >> /etc/locale.gen && locale-gen
RUN apt-get -y install --no-install-recommends tmux git ansible most curl yamllint python3-pkg-resources flake8 shellcheck pylint python-pip software-properties-common python-software-properties git-crypt openssh-client bash-completion && \
    add-apt-repository ppa:jonathonf/vim -y && \
    apt-get update && \
    apt-get install --no-install-recommends -y vim && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*
RUN pip install --upgrade pip && \
    pip install --upgrade setuptools && \
    pip install --user git+git://github.com/powerline/powerline && \
    pip install --user powerline-gitstatus
RUN mkdir -p ~/.vim/autoload && \
    curl -fLo ~/.vim/autoload/plug.vim https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
