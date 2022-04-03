# [ntp](#ntp)

|GitHub|GitLab|
|------|------|
|[![github](https://github.com/mullholland/ansible-role-ntp/workflows/Ansible%20Molecule/badge.svg)](https://github.com/mullholland/ansible-role-ntp/actions)|[![gitlab](https://gitlab.com/mullholland/ansible-role-ntp/badges/master/pipeline.svg)](https://gitlab.com/mullholland/ansible-role-ntp)|[![quality](https://img.shields.io/ansible/quality/unset)](https://galaxy.ansible.com/mullholland/ntp)|

Installs and configures the ntp/chrony daemon.

## [Role Variables](#role-variables)

These variables are set in `defaults/main.yml`:
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


## [Example Playbook](#example-playbook)

This example is taken from `molecule/default/converge.yml` and is tested on each push, pull request and release.
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





## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/mullholland):

-   [debian9](https://hub.docker.com/r/mullholland/docker-molecule-debian9)
-   [debian10](https://hub.docker.com/r/mullholland/docker-molecule-debian10)
-   [debian11](https://hub.docker.com/r/mullholland/docker-molecule-debian11)
-   [ubuntu1804](https://hub.docker.com/r/mullholland/docker-molecule-ubuntu1804)
-   [ubuntu2004](https://hub.docker.com/r/mullholland/docker-molecule-ubuntu2004)
-   [centos7](https://hub.docker.com/r/mullholland/docker-molecule-centos7)
-   [centos-stream8](https://hub.docker.com/r/mullholland/docker-molecule-centos-stream8)
-   [centos-stream9](https://hub.docker.com/r/mullholland/docker-molecule-centos-stream9)
-   [fedora34](https://hub.docker.com/r/mullholland/docker-molecule-fedora34)
-   [fedora35](https://hub.docker.com/r/mullholland/docker-molecule-fedora35)
-   [amazonlinux](https://hub.docker.com/r/mullholland/docker-molecule-amazonlinux)
-   [rockylinux8](https://hub.docker.com/r/mullholland/docker-molecule-rockylinux8)
-   [almalinux8](https://hub.docker.com/r/mullholland/docker-molecule-almalinux8)

The minimum version of Ansible required is 2.10, tests have been done to:

-   The previous versions.
-   The current version.



## [Exceptions](#exceptions)

Some variations of the build matrix do not work. These are the variations and reasons why the build won't work:

| variation                 | reason                 |
|---------------------------|------------------------|
| ubi8 | No chrony/ntp package in default repositories |


If you find issues, please register them in [GitHub](https://github.com/mullholland/ansible-role-ntp/issues)

## [License](#license)

MIT


## [Author Information](#author-information)

[Mullholland](https://github.com/mullholland)

## [Special Thanks](#special-thanks)

Template inspired by [Robert de Bock](https://github.com/robertdebock)
