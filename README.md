# Container image: Debian Ansible

[![Build Status](https://travis-ci.com/chzerv/docker-debian-ansible.svg?branch=master)](https://travis-ci.com/chzerv/docker-debian-ansible)

This Dockerfile builds a Debian-based container with Ansible and other Ansible testing tools pre-intalled.

# Branches/Tags

|  Branch  | Distribution version | Image tag |
| :------: | :------------------: | :-------: |
|  master  |     buster (10)      |  latest   |
| testing  |       bullseye       |  testing  |
| unstable |         sid          | unstable  |
| stretch  |     stretch (9)      |  stretch  |

# How to build locally

1. Install [Docker](https://docs.docker.com/engine/install/) or [Podman](https://podman.io/getting-started/installation.html).
2. Each branch represents a tag (version), with the `master` branch being the latest version. Clone the branch you're interested in. E.g., for Debian stretch: `git clone --branch=stretch https://github.com/chzerv/docker-debian-ansible.git`.
3. `cd` into the directory and run `docker build -t debian_stretch-ansible`

# How to use

1. Install [Docker](https://docs.docker.com/engine/install/) or [Podman](https://podman.io/getting-started/installation.html).
2. Pull this image from _Docker hub_: `docker pull chzerv/docker-debian-ansible:stretch`. Remember, the tag represents the distribution version, so change it according to your needs.
3. Run a container:

   ```shell
   docker run -d --privileged --volume=/sys/fs/cgroup:/sys/fs/cgroup:ro docker-debian-ansible:stretch
   ```

4. Run Ansible inside that container:

   ```shell
   docker exec -it $container_id ansible --version
   ```
