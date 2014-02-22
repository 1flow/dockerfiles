FROM        1flow-base
MAINTAINER  Olivier Cortès <oc@1flow.io>

ENV DEBIAN_FRONTEND noninteractive

RUN echo "force-unsafe-io" > /etc/dpkg/dpkg.cfg.d/02apt-speedup
RUN echo "Acquire::http {No-Cache=True;};" > /etc/apt/apt.conf.d/no-cache

#RUN echo $'#!/bin/sh\nexit 101' > /usr/sbin/policy-rc.d
#RUN chmod +x /usr/sbin/policy-rc.d

RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
# Update the package repository
RUN apt-get -q update && apt-get upgrade -q -y --force-yes

RUN apt-get -qqy install python-software-properties locales vim pwgen unzip curl wget git-core

# Configure timezone and locale
RUN echo "Europe/Paris" > /etc/timezone; dpkg-reconfigure -f noninteractive tzdata
RUN export LANGUAGE=en_US.UTF-8; export LANG=en_US.UTF-8; export LC_ALL=en_US.UTF-8; locale-gen en_US.UTF-8; DEBIAN_FRONTEND=noninteractive dpkg-reconfigure locales
