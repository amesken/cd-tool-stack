FROM sameersbn/postgresql:9.4-8

MAINTAINER Andries Mesken <andries.mesken@ziggo.nl>

RUN mkdir -p /c/Users/Andries/docker/data/postgresql/run && chmod 777 /c/Users/Andries/docker/data/postgresql/run && \ 
  mkdir -p /c/Users/Andries/docker/data/postgresql/data && chmod 777 /c/Users/Andries/docker/data/postgresql/data && \ 
  mkdir -p /c/Users/Andries/docker/data/postgresql/log && chmod 777 /c/Users/Andries/docker/data/postgresql/log

VOLUME ["/run/postgresql", "/var/lib/postgresql", "/var/log/postgresql"]
