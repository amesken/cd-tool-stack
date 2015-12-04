FROM sameersbn/postgresql:9.4-8

MAINTAINER Andries Mesken <andries.mesken@ziggo.nl>

RUN mkdir -p /d/docker/data/postgresql/run && chmod 777 /d/docker/data/postgresql/run && \ 
  mkdir -p /d/docker/data/postgresql/data && chmod 777 /d/docker/data/postgresql/data && \ 
  mkdir -p /d/docker/data/postgresql/log && chmod 777 /d/docker/data/postgresql/log

VOLUME ["/run/postgresql", "/var/lib/postgresql", "/var/log/postgresql"]
