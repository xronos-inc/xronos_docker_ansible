# Ansible role for installing docker on a host

Features:

- installs latest docker-ce
- installs docker python module
- installs docker-compose
- (optional) installs support for docker buildx multiarchitecture builds
- (optional) performs a docker system prune

## Requirements

Provisioning host:

- ansible 2.15 or later

Host that will run docker

- Ubuntu 22.04 or later (or equivalent Debian-based distro running apt)

## How to use this role

Add this role to your Ansible playbook file.

```yaml
- name: install docker
  role: xronos_docker_ansible
```

## Variables

- `docker_prune` (= `true`): prune docker containers, images and networks.
- `docker_multiarch` (= `false`): install QEMU and optionally containerd-shapshot.
- `docker_multiarch_containerd_snapshot` (= `false`): use containerd-shapshot and create a buildx builder using the `docker-container` driver. Ignored if `docker_multiarch` is false.
- `docker_multiarch_containerd_builder_name` (= `multiarch`): docker buildx container name for multiarchitecture builds. Used only if `docker_multiarch` and `docker_multiarch_containerd_snapshot` are true.
- `docker_auth` (= `''`): docker authentication token. When present, is written to the user's docker config.json.
- `docker_add_ansible_user_to_docker_group` (= `true`): Add current Ansible user to group 'docker'?