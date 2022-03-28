The Dockerfiles in this directory can be used to build multi architecture container
images using something along the lines of the following. This assumes that the
appropriate buildx builder instances have been created according to the insructions
at https://github.com/docker/buildx. It has been tried with docker desktop 4.6.1
on macOS 12.3 arm64.

```sh
$ VERSION=22 REPO=my_docker_hub_namespace \
  docker buildx build --platform linux/amd64,linux/arm64 \
  -t $REPO/kind-node:$VERSION -f Dockerfile.$VERSION . --push
```
