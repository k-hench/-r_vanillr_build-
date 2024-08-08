# README for `r_vanillr`

Github repository for the [podman](https://podman.io/) container [`r_vanillr`](https://hub.docker.com/repository/docker/khench/r_vanillr).

## Documentation of the initial setup

Originally, the `r_vanillr` container was build using [buildah](https://buildah.io/), from the accompanying `Containerfile`:

```sh
buildah bud -t r_vanillr
```

To make the container publicly available, it is pushed to [dockerhub](https://hub.docker.com/r/khench/r_vanillr) using [skopeo](https://github.com/containers/skopeo) and [podman](https://podman.io/):

```sh
skopeo login -u khench docker.io
podman push localhost/r_vanillr docker.io/khench/r_vanillr:v0.1
```

## Accessing the container

The bundled software can be accessed directly from [dockerhub](https://hub.docker.com/r/khench/r_vanillr) with `podman` (or `docker`, or `singularity` / `apptainer`):

```sh
podman run docker.io/khench/r_vanillr:v0.1 R --version
```
