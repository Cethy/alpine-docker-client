Alpine-docker-client
===

Simple docker image based on alpine3.6 with docker client (`17.06.2-ce`) installed.

- **install docker client**
    - install curl
    - fetch docker binaries archive
    - unzip archive
    - move docker client binary
    - remove curl & cleanup artifacts

| **ENTRYPOINT** | **CMD** |
|:---:|:---:|
| `docker` | `-v` |

## How to use (running docker instructions)
Since this image is designed to work with the host docker engine, you need to pass the socket.

    # display stats
    docker run -it -v /var/run/docker.sock:/var/run/docker.sock cethy/alpine-docker-client stats

## Using another docker version
Example building a new image with another docker client :

    docker build --build-arg DOCKER_CLI_VERSION="17.03.1-ce" -t my-alpine-docker .
    docker run my-alpine-docker
    # will output : Docker version 17.03.1-ce, build c6d412e

## Docker releases listing
[https://download.docker.com/linux/static/stable/x86_64/](https://download.docker.com/linux/static/stable/x86_64/)
