FROM ubuntu:22.04
RUN echo 'APT::Install-Suggests "0";' >> /etc/apt/apt.conf.d/00-docker
RUN echo 'APT::Install-Recommends "0";' >> /etc/apt/apt.conf.d/00-docker
RUN DEBIAN_FRONTEND=noninteractive \
    apt-get update \
    && apt-get install -y build-essential g++ manpages-dev python3 python3-dev python3-pip libsasl2-dev libsasl2-2 libsasl2-modules-gssapi-mit\
    && rm -rf /var/lib/apt/lists/*
COPY requirements.txt /tmp/requirements.txt    
RUN pip3 install -r /tmp/requirements.txt
RUN apt-get update \
    && apt-get install -y openssh-server \
    && systemctl ssh start \
    && systemctl ssh enable
RUN useradd -ms /bin/bash apprunner
USER apprunner