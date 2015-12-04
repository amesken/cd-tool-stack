FROM sameersbn/redis

MAINTAINER Andries Mesken <andries.mesken@ziggo.nl>

RUN mkdir -p /d/docker/data/redis/data && chmod 777 /d/docker/data/redis/data \
  && mkdir -p /d/docker/data/redis/log && chmod 777 /d/docker/data/redis/log

VOLUME ["/var/lib/redis", "/var/log/redis"]  