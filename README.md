# Environment of nodejs project [![.github/workflows/ci.yml](https://github.com/kernblick/nodejs-docker/workflows/.github/workflows/ci.yml/badge.svg)](https://github.com/kernblick/nodejs-docker/actions)

```bash
    [+] AUTOR:        Markus Luckey
    [+] CREDITS:      Gerardo Junior
    [+] SITE:         https://kernblick.de
    [+] EMAIL:        luckey@kernblick.de
    [+] GITHUB:       https://github.com/kernblick/nodejs-docker.git
```

Docker image to run [node](https://nodejs.org/) projects

> The project must be in the **/src** container folder

## Tags available

- [latest](https://github.com/kernblick/nodejs-docker/blob/develop/Dockerfile)
  - [library/node](https://hub.docker.com/_/node) 17.1.0-alpine
    - [node](https://nodejs.org/) 17.1.0
    - [yarn](https://yarnpkg.com/) 1.22.15

## Run

```bash
docker pull kernblick/nodejs:latest
docker run kernblick/nodejs
```

## How to build

to build the image you need install the [docker engine](https://www.docker.com/) only

> You can try building with different versions of software with docker args, for example: NODE_VERISON=16.13.0

```bash
docker build https://github.com/kernblick/nodejs-docker.git --tag kernblick/nodejs
```

## How to use

### With [docker](https://docs.docker.com/engine/reference/commandline/docker/) command

```bash
docker run -it --rm kernblick/nodejs:latest [sh command or npm script]
```

### With [docker-compose](https://docs.docker.com/compose/) command

Create the [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file  in your project folder with:

```yml
# (...)

  nodejs:
    image: kernblick/nodejs:latest
    restart: on-failure

# (...)
```

run this command with this syntax

```bash
docker-compose run node [sh command or npm script]
```

## How to enter image shell

```bash
docker run -it --rm kernblick/nodejs sh
# or with docker-compose
docker-compose run node sh
```

## License

This project is licensed under the MIT License - see the [LICENSE](https://github.com/kernblick/nodejs-docker/blob/master/LICENSE) file for details
