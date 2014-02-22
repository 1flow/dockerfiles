FROM        1flow-base
MAINTAINER  Olivier Cortès <oc@1flow.io>

RUN DEBIAN_FRONTEND=noninteractive apt-get install -q -y memcached

USER daemon

EXPOSE 11211

CMD ["memcached", "-m", "1024"]
