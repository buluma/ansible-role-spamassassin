# Ansible role [spamassassin](https://galaxy.ansible.com/ui/standalone/roles/buluma/spamassassin/documentation)

Install and configure spamassassin on your system.

|GitHub|Version|Issues|Pull Requests|Downloads|
|------|-------|------|-------------|---------|
|[![github](https://github.com/buluma/ansible-role-spamassassin/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-spamassassin/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-spamassassin.svg)](https://github.com/buluma/ansible-role-spamassassin/releases/)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-spamassassin.svg)](https://github.com/buluma/ansible-role-spamassassin/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-spamassassin.svg)](https://github.com/buluma/ansible-role-spamassassin/pulls/)|[![Ansible Role](https://img.shields.io/ansible/role/d/buluma/spamassassin)](https://galaxy.ansible.com/ui/standalone/roles/buluma/spamassassin/documentation)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-spamassassin/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: yes
  gather_facts: yes

  roles:
    - role: buluma.spamassassin
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-spamassassin/blob/master/molecule/default/prepare.yml):

```yaml
---
- name: Prepare
  hosts: all
  gather_facts: no
  become: yes

  roles:
    - role: buluma.bootstrap
    - role: buluma.core_dependencies
    - role: buluma.cron
    - role: buluma.logrotate
      logrotate_entries:
        - name: spamassassin
          path: /var/log/spamassassin
          missingok: yes
    - role: buluma.rsyslog
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-spamassassin/blob/master/defaults/main.yml):

```yaml
---
# defaults file for spamassassin

# What group and user spamd should run under.
spamassassin_group: spamd
spamassassin_user: spamd
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-spamassassin/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | Version |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Ansible Molecule](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-bootstrap.svg)](https://github.com/shadowwalker/ansible-role-bootstrap)|
|[buluma.core_dependencies](https://galaxy.ansible.com/buluma/core_dependencies)|[![Ansible Molecule](https://github.com/buluma/ansible-role-core_dependencies/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-core_dependencies/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-core_dependencies.svg)](https://github.com/shadowwalker/ansible-role-core_dependencies)|
|[buluma.cron](https://galaxy.ansible.com/buluma/cron)|[![Ansible Molecule](https://github.com/buluma/ansible-role-cron/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-cron/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-cron.svg)](https://github.com/shadowwalker/ansible-role-cron)|
|[buluma.logrotate](https://galaxy.ansible.com/buluma/logrotate)|[![Ansible Molecule](https://github.com/buluma/ansible-role-logrotate/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-logrotate/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-logrotate.svg)](https://github.com/shadowwalker/ansible-role-logrotate)|
|[buluma.rsyslog](https://galaxy.ansible.com/buluma/rsyslog)|[![Ansible Molecule](https://github.com/buluma/ansible-role-rsyslog/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-rsyslog/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-rsyslog.svg)](https://github.com/shadowwalker/ansible-role-rsyslog)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-spamassassin/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|[Alpine](https://hub.docker.com/repository/docker/buluma/alpine/general)|all|
|[EL](https://hub.docker.com/repository/docker/buluma/enterpriselinux/general)|8|
|[Debian](https://hub.docker.com/repository/docker/buluma/debian/general)|all|
|[Fedora](https://hub.docker.com/repository/docker/buluma/fedora/general)|all|
|[opensuse](https://hub.docker.com/repository/docker/buluma/opensuse/general)|all|
|[Ubuntu](https://hub.docker.com/repository/docker/buluma/ubuntu/general)|all|

The minimum version of Ansible required is 2.12, tests have been done to:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-spamassassin/issues)

## [Changelog](#changelog)

[Role History](https://github.com/buluma/ansible-role-spamassassin/blob/master/CHANGELOG.md)

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-spamassassin/blob/master/LICENSE)

## [Author Information](#author-information)

[Shadow Walker](https://buluma.github.io/)

