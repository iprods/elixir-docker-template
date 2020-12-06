FROM hexpm/elixir:1.11.2-erlang-23.1.4-debian-buster-20201012
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

#RUN curl -sL https://deb.nodesource.com/setup_12.x | bash - && \
#    apt-get install -y inotify-tools nodejs

RUN mkdir /app
WORKDIR /app

RUN mix local.hex --force \
    && mix local.rebar --force \
#    && mix archive.install hex phx_new 1.5.7 --force \
    && echo

COPY run.sh /

