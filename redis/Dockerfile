FROM sameersbn/redis

MAINTAINER Andries Mesken <andries.mesken@ziggo.nl>

RUN mkdir -p /c/Users/Andries/docker/data/redis/data && chmod 777 /c/Users/Andries/docker/data/redis/data \
  && mkdir -p /c/Users/Andries/docker/data/redis/log && chmod 777 /c/Users/Andries/docker/data/redis/log

VOLUME ["/var/lib/redis", "/var/log/redis"]  