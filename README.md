# Docker in Docker image with up-to-date armhf support

[![Build Status](https://ci.strahlungsfrei.de/api/badges/djmaze/dind-image-with-armhf/status.svg)](https://ci.strahlungsfrei.de/djmaze/dind-image-with-armhf)

[The official docker-in-docker image](https://hub.docker.com/_/docker) does not contain an up-to-date armhf version. The official builds are not working anymore [since 19.03](https://github.com/docker-library/docker/issues/260).

Turns out building the latest versions of the docker daemon using the golang images in a container will always yield a broken executable on armhf.

For that reason, this image contains armhf binaries [built manually on a armhf machine](https://github.com/djmaze/docker-armhf-binaries).

## How to use

This image should be fully compatible with the official [`docker`](https://github.com/djmaze/docker-armhf-binaries) image, so you just need to replace `docker` with `mazzolino/docker` in your builds or configurations.

The `latest` tag is not supported currently, so you need to specify a version, e.g. `mazzolino/docker:20`.

Also, for now only the following architectures are supported:

- amd64
- arm64
- armhf
