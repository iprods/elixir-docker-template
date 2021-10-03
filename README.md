# Elixir Docker Template

This template contains the boilerplate to setup an Elixir application via
Docker.

## Motivation

As Elixir (as well as other languages) has different versions and prerequisites
this template should help being able to have multiple versions at once. There
are other ways like f.e. `asdf` to achieve this but for quickly checking out a
project for instance Docker is a nice solution.

Further this should help to get other people onboarded more easily as the stack
specific are "hidden" by Docker.

Lastly the ability to develop under a production alike system environment might
help to miss some hurdles.

## Features

- Docker based environment for Elixir / Erlang
- Development script for easier handling of the stack

## Prerequisites

You need to have the following installed:

- [Docker](https://docker.io) for running the code
- [Mutagen](https://mutagen.io) for code syncing (optional)

> Mutagen is used to overcome the slow bind mounting on platforms like macOS.
> Note that the use of Mutagen is optional.

## Usage

To use the template either download the files and augment an existing project
or use this template as a starting point.

Per default the template does start an IEx session without anything else.

### Create a mix project

To use the template for a mix based environment you can use the `dev` script by
running:

```
./dev create mix new . --app my_app  # Create a mix app name `my_app`
```

> After setting up the project you likely want to change the `docker/app/run.sh`
> script and execute `iex -S mix` instead of only `iex`.

### The `dev` script

You can use the `dev` script to perform some common tasks like spinning up the
stack.

To see the supported commands you can run:

```
$ ./dev
```

> This will list all available commands. These can be easily extended by adding
> new functions to either the `.dev` directory or in the `dev` script itself.
> This is as well meant to be a starting point.

### Customization of the Docker stack

The template has a fairly simple stack setup via Docker. But there are some
commented lines that can be easily commented in to install f.e. the dependencies
on container start as well as spawning a `phx.server` via the
`docker/app/run.sh` script and/or add a database via the `docker-compose.yml`.

#### Renaming containers

You might want to adapt the naming of the Docker stack images like use something
more meaningful than f.e. `template-mutagen` for the sync container. Please check
and replace occurrences in the followind file:

- `docker-compose.yml`
- `mutagen.yml`

## License

MIT
