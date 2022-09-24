FROM hexpm/elixir:1.14.0-erlang-25.0.4-debian-bullseye-20220801-slim
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
  inotify-tools\
  apt-transport-https

RUN mkdir /app
WORKDIR /app

RUN mix local.hex --force \
  && mix local.rebar --force \
  #    && mix archive.install hex phx_new --force \
  && echo

COPY run.sh /

