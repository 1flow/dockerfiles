FROM        1flow-base
MAINTAINER  Olivier Cortès <oc@1flow.io>

RUN apt-add-repository -y ppa:chris-lea/redis-server
RUN apt-get update -q -y
RUN DEBIAN_FRONTEND=noninteractive apt-get install -q -y redis-server

EXPOSE 6379

ADD redis.conf /etc/redis/redis.conf
ENTRYPOINT ["redis-server"]
