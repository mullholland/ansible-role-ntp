# [ntp](#ntp)

Installs and configures the ntp/chrony daemon.

|GitHub|GitLab|Quality|Downloads|Version|
|------|------|-------|---------|-------|
|[![github](https://github.com/mullholland/ansible-role-ntp/workflows/Ansible%20Molecule/badge.svg)](https://github.com/mullholland/ansible-role-ntp/actions)|[![gitlab](https://gitlab.com/opensourceunicorn/ansible-role-ntp/badges/master/pipeline.svg)](https://gitlab.com/opensourceunicorn/ansible-role-ntp)|[![quality](https://img.shields.io/ansible/quality/57681)](https://galaxy.ansible.com/mullholland/ntp)|[![downloads](https://img.shields.io/ansible/role/d/57681)](https://galaxy.ansible.com/mullholland/ntp)|[![Version](https://img.shields.io/github/release/mullholland/ansible-role-ntp.svg)](https://github.com/mullholland/ansible-role-ntp/releases/)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/mullholland/ansible-role-ntp/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: true
  gather_facts: true
  vars:
    # Molecule tests sometime fail with chronyd in the container
    # so we disable it for testing
    ntp_state: "stopped"
    ntp_enabled: "false"
  roles:
    - role: "mullholland.ntp"
```


## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/mullholland/ansible-role-ntp/blob/master/defaults/main.yml):

```yaml
---
ntp_servers:
 - 0.de.pool.ntp.org iburst
 - 1.de.pool.ntp.org iburst
 - 2.de.pool.ntp.org iburst
 - 3.de.pool.ntp.org iburst

# Manage the ntp/chronyd daemon
ntp_state: started
ntp_enabled: true
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/mullholland/ansible-role-ntp/blob/master/requirements.txt).


## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://mullholland.net) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/mullholland/ansible-role-ntp/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/mullholland):

|container|tags|
|---------|----|
|[EL](https://hub.docker.com/repository/docker/mullholland/docker-centos-systemd/general)|all|
|[Amazon](https://hub.docker.com/repository/docker/mullholland/docker-amazonlinux-systemd/general)|Candidate|
|[Fedora](https://hub.docker.com/repository/docker/mullholland/docker-fedora-systemd/general)|all|
|[Ubuntu](https://hub.docker.com/repository/docker/mullholland/docker-ubuntu-systemd/general)|all|
|[Debian](https://hub.docker.com/repository/docker/mullholland/docker-debian-systemd/general)|all|

The minimum version of Ansible required is 2.10, tests have been done to:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them in [GitHub](https://github.com/mullholland/ansible-role-ntp/issues)

## [License](#license)

[MIT](https://github.com/mullholland/ansible-role-ntp/blob/master/LICENSE).

## [Author Information](#author-information)

[Mullholland](https://mullholland.net)

Please consider [sponsoring me](https://github.com/sponsors/mullholland).
