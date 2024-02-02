# Ansible role for installing docker on a host
Features:
- installs latest docker-ce
- installs docker python module
- installs docker-compose
- (optional) installs support for docker buildx multiarchitecture builds
- (optional) performs a docker system prune

This role derives from [elgeeko1/elgeeko1-docker-ansible](https://github.com/elgeeko1/elgeeko1-docker-ansible)

# Requirements
Provisioning host:
- ansible 2.15 or later

Host that will run docker
- Ubuntu 22.04 or later (or equivalent Debian-based distro running apt)

# How to use this role

Add this role to your Ansible playbook file.
```yaml
- name: install docker
  role: xronos-docker-ansible
```

## Variables

- `docker_prune` (= `true`): prune docker containers, images and networks.
- `docker_multiarch` (= `false`): install docker buildx for multiarch builds. Configures a docker buildx instance using the docker-container driver and QEMU.
- `docker_multiarch_builder_name` (= `multiarch`): docker buildx container name for multiarchitecture builds.