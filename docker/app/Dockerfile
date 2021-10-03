FROM hexpm/elixir:1.11.4-erlang-23.3.1-debian-buster-20210326
# Install basic dependencies see https://medium.com/@ricardo.trindade743/setting-up-phoenix-postgresql-with-docker-compose-for-local-development-afeb4a4ace6c
RUN apt-get update -qq && \
    apt-get -y --allow-unauthenticated install\
      build-essential\
      curl\
      libpq-dev\
#      postgresql-client\
      git\
      make\
      erlang-crypto\
      apt-transport-https

RUN mkdir /app
WORKDIR /app

RUN mix local.hex --force \
    && mix local.rebar --force \
#    && mix archive.install hex phx_new 1.6.0 --force \
    && echo

COPY run.sh /

