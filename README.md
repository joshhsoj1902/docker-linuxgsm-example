# docker-linuxgsm-example

This repo is meant to show how [this pr](https://github.com/GameServerManagers/docker-linuxgsm/pull/36) could be used

```bash

# Build the base image from the PR (Checkout my branch from that PR and build the docker image there)
docker build -t example/linuxgsm:ubuntu-22.04 -f ./Dockerfile.ubuntu-2204 .

# Build the "offical" pmc image using the custom base image (Assuming this example repo is checked out, this image can be built right here)
docker build -t example/linuxgsm:pmc -f ./Dockerfile.pmc .



# Now an end-user can build a custom image with LGSM as the base
docker build -t example/paper-mc:latest -f ./Dockerfile .

# Now if we run the newly built image, and we're quick, we should notice each of the scripts in the hook dir get executed.
docker run --rm  --name paper-mc example/paper-mc:latest

```
