FROM sshd:latest

MAINTAINER Dimitri Justeau <dimitri.justeau@gmail.com>

# Add latest R jessie backports to sources.list
RUN echo "deb http://cran.stat.auckland.ac.nz/bin/linux/debian jessie-cran3/" >> /etc/apt/sources.list \
    && apt-key adv --keyserver keys.gnupg.net --recv-key 6212B7B7931C4BB16280BA1306F90DE5381BA480

# Taken from officiel R-base Dockerfile
RUN apt-get update \
    && apt-get install -y \
        sudo \
        ed \
        less \
        locales \
        vim-tiny \
        nano \
        wget \
        tmux \
        ca-certificates \
        git \
        libcurl3 libcurl3-dev \
        openssl libssl-dev \
        libxml2 libxml2-dev \
        gsl-bin libgsl0-dev

# Configure default locale, see https://github.com/rocker-org/rocker/issues/19
RUN echo "fr_FR.UTF-8 UTF-8" >> /etc/locale.gen \
    && locale-gen fr_FR.utf8 \
    && /usr/sbin/update-locale LANG=fr_FR.UTF-8

ENV LC_ALL fr_FR.UTF-8
ENV LANG fr_FR.UTF-8

# Install R
RUN apt-get install -y r-base r-base-dev

RUN apt-get install -y software-properties-common python-software-properties

