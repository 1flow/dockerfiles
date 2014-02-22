FROM 1flow-base
MAINTAINER Olivier Cortès <oc@1flow.io>

ENV PG_VERSION 9.2
ENV USER oneflow_admin
ENV PASS verjedJajteunyeksyotgapUnnyunFog

RUN echo "deb http://apt.postgresql.org/pub/repos/apt/ precise-pgdg main" > /etc/apt/sources.list.d/pgdg.list
RUN wget -q https://www.postgresql.org/media/keys/ACCC4CF8.asc -O - | apt-key add -
RUN apt-get -qq update

RUN apt-get -qqy install postgresql-$PG_VERSION postgresql-contrib-$PG_VERSION

ADD postgresql.conf etc/postgresql/$PG_VERSION/main/postgresql.conf
ADD pg_hba.conf etc/postgresql/$PG_VERSION/main/pg_hba.conf
ADD run_postgresql.sh run_postgresql.sh

EXPOSE 5432
RUN rm /usr/sbin/policy-rc.d
CMD ["/run_postgresql.sh"]
