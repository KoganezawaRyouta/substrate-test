FROM rust:1.33.0

RUN apt-get update && \
    apt-get install -y libusb-1.0-0-dev libudev-dev cmake make gcc g++ pkg-config file

RUN mkdir /app
WORKDIR /app
COPY . /app

# Add a script to be executed every time the container starts.
COPY ./docker/rust/entrypoint.sh /usr/bin/
RUN chmod +x /usr/bin/entrypoint.sh
ENTRYPOINT ["entrypoint.sh"]
