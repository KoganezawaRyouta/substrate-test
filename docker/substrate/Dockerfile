FROM ubuntu:16.04

RUN \
  apt-get update && \
  apt-get -y install make git bash curl unzip && \
  apt-get update

RUN curl https://getsubstrate.io -sSf | bash

# Add a script to be executed every time the container starts.
COPY ./docker/substrate/entrypoint.sh /usr/bin/
RUN chmod +x /usr/bin/entrypoint.sh
ENTRYPOINT ["entrypoint.sh"]