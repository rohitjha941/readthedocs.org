FROM ubuntu:18.04

ENV DEBIAN_FRONTEND noninteractive
ENV LANG C.UTF-8

WORKDIR /usr/src/app

RUN apt-get -y update
RUN apt-get -y install \
        curl \
        g++ \
        git-core \
        libevent-dev \
        libpq-dev \
        libxml2-dev \
        libxslt1-dev \
        build-essential \
        python3-pip \
        python3-dev \
        postgresql-client \
        libmysqlclient-dev \
        libfreetype6 \
        libjpeg-dev \
        sqlite

RUN pip3 install --no-cache-dir --upgrade pip

RUN mkdir checkouts
WORKDIR /usr/src/app/checkouts

COPY requirements readthedocs.org/requirements

RUN pip3 install --no-cache-dir -r readthedocs.org/requirements/docker.txt

WORKDIR /usr/src/app/checkouts/readthedocs.org
