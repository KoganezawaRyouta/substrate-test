FROM ubuntu:16.04

RUN \
  apt-get update && \
  apt-get -y install make git bash curl unzip build-essential && \
  apt-get update

RUN curl https://sh.rustup.rs -sSf | sh -s -- -y
RUN echo 'source $HOME/.cargo/env' >> ~/.bashrc
RUN mkdir /app
WORKDIR /app
COPY . /app

# Add a script to be executed every time the container starts.
COPY ./docker/rust/entrypoint.sh /usr/bin/
RUN chmod +x /usr/bin/entrypoint.sh
ENTRYPOINT ["entrypoint.sh"]
