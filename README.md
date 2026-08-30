# [Ansible role ansible-generator](#ansible-generator)

Installs and configures the ntp/chrony daemon.

|GitHub|Downloads|Version|
|------|---------|-------|
|[![github](https://github.com/mullholland/ansible-role-ansible-generator/actions/workflows/molecule.yml/badge.svg)](https://github.com/mullholland/ansible-role-ansible-generator/actions/workflows/molecule.yml)|[![downloads](https://img.shields.io/ansible/role/d/mullholland/ansible-generator)](https://galaxy.ansible.com/mullholland/ansible-generator)|[![Version](https://img.shields.io/github/release/mullholland/ansible-role-ansible-generator.svg)](https://github.com/mullholland/ansible-role-ansible-generator/releases/)|
## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/mullholland/ansible-role-ansible-generator/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  gather_facts: true
  vars:
    # Molecule tests sometime fail with chronyd in the container
    # so we disable it for testing
    ntp_state: "stopped"
    ntp_enabled: "false"
  roles:
    - role: "{{ lookup('env', 'MOLECULE_PROJECT_DIRECTORY') }}"
```


## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/mullholland/ansible-role-ansible-generator/blob/master/defaults/main.yml):

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

- pip packages listed in [requirements.txt](https://github.com/mullholland/ansible-role-ansible-generator/blob/master/requirements.txt).


## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://mullholland.net) for further information.

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/mullholland):

|container|tags|
|---------|----|
|[EL](https://hub.docker.com/r/mullholland/enterpriselinux)|all|
|[Rocky](https://hub.docker.com/r/mullholland/rockylinux)|all|
|[AlmaLinux](https://hub.docker.com/r/mullholland/almalinux)|all|
|[Amazon](https://hub.docker.com/r/mullholland/amazonlinux)|all|
|[Fedora](https://hub.docker.com/r/mullholland/fedora/)|all|
|[Ubuntu](https://hub.docker.com/r/mullholland/ubuntu)|all|
|[Debian](https://hub.docker.com/r/mullholland/debian)|all|
|[CentOS](https://hub.docker.com/r/mullholland/centos)|all|

The minimum version of Ansible required is 2.10, tests have been done to:

- The version before the previous version.
- The previous version.
- The current version.

If you find issues, please register them in [GitHub](https://github.com/mullholland/ansible-role-ansible-generator/issues).

## [License](#license)

[MIT](https://github.com/mullholland/ansible-role-ansible-generator/blob/master/LICENSE).

## [Author Information](#author-information)

[Mullholland](https://mullholland.net)
