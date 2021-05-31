#################################################################
# Dockerfile to build Zimbra Collaboration 8.8.7 container images
# Based on Ubuntu 16.04
#################################################################
FROM ubuntu:16.04

RUN echo "resolvconf resolvconf/linkify-resolvconf boolean false" | debconf-set-selections

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get -y install \
  wget \
  dialog \
  openssh-client \
  software-properties-common \
  dnsmasq \
  dnsutils \
  net-tools \
  sudo \
  rsyslog \
  unzip

RUN apt-get update -y
RUN apt-get install -y software-properties-common
RUN apt-get install -y language-pack-en-base
RUN export LC_ALL=en_US.UTF-8 && export LANG=en_US.UTF-8

RUN apt-get update -y && apt-get install -y iputils-ping

VOLUME ["/opt/zimbra"]

EXPOSE 22 25 465 587 110 143 993 995 80 443 8080 8443 7071

COPY opt /opt/

COPY etc /etc/

CMD ["/bin/bash", "/opt/start.sh", "-d"]
