# Debian 10 (Buster) Image for Ansible Testing

![Build](https://github.com/chzerv/docker-debian-ansible/workflows/Build/badge.svg?branch=master)
![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/chzerv/docker-debian-ansible)

This Dockerfile builds a Debian 10 based container, capable to use `systemd`, with Ansible and Ansible 
testing tools pre-installed.

# Branches/Tags

Each branch of this repository represents a Debian version, with the `master` branch representing the
latest version. Pull the branch (version) you are interested in.

| Branch   | Distribution version | Image tag            |
| :------: | :------------------: | :-------:            |
| master   | buster (10)          | latest,10            |
| testing  | bullseye             | testing              |
| unstable | sid                  | unstable             |
| stretch  | stretch (9)          | stretch [deprecated] |

# How to build locally

1. Install [Docker](https://docs.docker.com/engine/install/) or [Podman](https://podman.io/getting-started/installation.html).
2. Clone the branch you're interested in. For example, for Debian 10 (buster): `git clone https://github.com/chzerv/docker-debian-ansible.git`.
3. `cd` into the directory and run `docker build -t debian10-ansible .`

# How to use

1. Install [Docker](https://docs.docker.com/engine/install/) or [Podman](https://podman.io/getting-started/installation.html).
2. Pull this image from _Docker hub_: `docker pull chzerv/docker-debian-ansible:latest` (or use the 
   image you built locally).
3. Run a container:

   ```shell
   docker run -d --privileged --volume=/sys/fs/cgroup:/sys/fs/cgroup:ro docker-debian-ansible:latest
   ```

4. Run Ansible inside that container:

   ```shell
   docker exec -it $container_id ansible --version
   ```

# Notes

This image is used for testing Ansible roles and playbooks locally and/or in CI, hence, security is not
a concern. It is not intended or recommended to use this image in production environments.
