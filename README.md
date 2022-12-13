# Docker image for tchap-web-v4

[![Docker](https://github.com/tchapgouv/tchap-web-v4-docker/actions/workflows/docker.yml/badge.svg)](https://github.com/tchapgouv/tchap-web-v4-docker/actions/workflows/docker.yml)

This repo only hosts Github Action CI to build the docker image from the [tchap-web-v4 repo](https://github.com/tchapgouv/tchap-web-v4/).

## Pull image

```
docker login ghcr.io --username <github_username> --password-stdin
docker pull ghcr.io/tchapgouv/tchap-web-v4:latest
```

## Release

Docker image is build daily if new tag is detected on tchap-web-v4 repo on `develop_tchap` branch

Two images are created: `tchap-web-v4:latest` and `tchap-web-v4:tag_version`

