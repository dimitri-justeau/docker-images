FROM sshd:latest

MAINTAINER Dimitri Justeau <dimitri.justeau@gmail.com>

RUN apt-get update && apt-get install -y wget unzip

#installs mothur
RUN wget https://github.com/mothur/mothur/releases/download/v1.38.1/Mothur.linux_64.zip && \
    unzip Mothur.linux_64.zip && \
    rm Mothur.linux_64.zip && \
    rm -rf __MACOSX

#adds executables to the path
ENV PATH /mothur:$PATH

