FROM sameersbn/gitlab:8.2.2

MAINTAINER Andries Mesken <andries.mesken@ziggo.nl>

RUN mkdir -p /c/Users/Andries/docker/data/gitlab/data && chmod 777 /c/Users/Andries/docker/data/gitlab/data && \
  mkdir -p /c/Users/Andries/docker/data/gitlab/log && chmod 777 /c/Users/Andries/docker/data/gitlab/log

VOLUME ["/home/git/data", "/var/log/gitlab"]
