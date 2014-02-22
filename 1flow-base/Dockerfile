FROM        1flow-base
MAINTAINER  Olivier Cortès <oc@1flow.io>

# Update apt sources
RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list

# Update the package repository
RUN apt-get -q update && apt-get upgrade -q -y --force-yes

RUN DEBIAN_FRONTEND=noninteractive apt-get install -q -y locales wget

# Configure timezone and locale
RUN echo "Europe/Paris" > /etc/timezone; dpkg-reconfigure -f noninteractive tzdata
RUN export LANGUAGE=en_US.UTF-8; export LANG=en_US.UTF-8; export LC_ALL=en_US.UTF-8; locale-gen en_US.UTF-8; DEBIAN_FRONTEND=noninteractive dpkg-reconfigure locales
