# Ansible role for installing docker on a host
Features:
- installs latest docker-ce
- installs docker python module
- installs docker-compose
- TODO: docker plugins
- (optional) performs a docker system prune

This role derives from [elgeeko1/elgeeko1-docker-ansible](https://github.com/elgeeko1/elgeeko1-docker-ansible)

# Requirements
Provisioning host:
- ansible 2.15 or later

Host that will run docker
- Ubuntu 22.04 or later (or equivalentr Debian-based Linux distro running apt)

# How to use this role

Add this role to your Ansible playbook file.
```yaml
- name: install docker
  role: xronos-docker-ansible
```

## Variables

- `docker_prune`: prune docker containers, images and networks. Defaults to `true`
