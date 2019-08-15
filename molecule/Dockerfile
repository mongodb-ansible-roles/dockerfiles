FROM docker as docker

FROM debian:10
COPY --from=docker /usr/local/bin/docker /usr/local/bin/docker
RUN apt-get update && apt-get -qq install \
    build-essential \
    python \
    python-pip \
    ruby \
    ruby-dev
RUN gem install rubocop
RUN pip install docker molecule
ENTRYPOINT ["molecule"]
