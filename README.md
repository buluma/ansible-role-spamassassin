# [Ansible role spamassassin](#ansible-role-spamassassin)

Install and configure spamassassin on your system.

|GitHub|Issues|Pull Requests|Version|Downloads|
|------|------|-------------|-------|---------|
|[![github](https://github.com/buluma/ansible-role-spamassassin/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-spamassassin/actions/workflows/molecule.yml)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-spamassassin.svg)](https://github.com/buluma/ansible-role-spamassassin/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-spamassassin.svg)](https://github.com/buluma/ansible-role-spamassassin/pulls/)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-spamassassin.svg)](https://github.com/buluma/ansible-role-spamassassin/releases/)|[![Ansible Role](https://img.shields.io/ansible/role/d/buluma/spamassassin)](https://galaxy.ansible.com/ui/standalone/roles/buluma/spamassassin/documentation)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-spamassassin/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- become: true
  gather_facts: true
  hosts: all
  name: Converge
  roles:
    - role: buluma.spamassassin
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-spamassassin/blob/master/molecule/default/prepare.yml):

```yaml
---
- become: true
  gather_facts: false
  hosts: all
  name: Prepare
  roles:
    - role: buluma.bootstrap
    - role: buluma.core_dependencies
    - role: buluma.cron
    - logrotate_entries:
        - missingok: true
          name: spamassassin
          path: /var/log/spamassassin
      role: buluma.logrotate
    - role: buluma.rsyslog
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-spamassassin/blob/master/defaults/main.yml):

```yaml
---
spamassassin_group: spamd
spamassassin_user: spamd
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-spamassassin/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub |
|-------------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Build Status GitHub](https://github.com/buluma/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions)|
|[buluma.core_dependencies](https://galaxy.ansible.com/buluma/core_dependencies)|[![Build Status GitHub](https://github.com/buluma/ansible-role-core_dependencies/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-core_dependencies/actions)|
|[buluma.cron](https://galaxy.ansible.com/buluma/cron)|[![Build Status GitHub](https://github.com/buluma/ansible-role-cron/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-cron/actions)|
|[buluma.logrotate](https://galaxy.ansible.com/buluma/logrotate)|[![Build Status GitHub](https://github.com/buluma/ansible-role-logrotate/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-logrotate/actions)|
|[buluma.rsyslog](https://galaxy.ansible.com/buluma/rsyslog)|[![Build Status GitHub](https://github.com/buluma/ansible-role-rsyslog/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-rsyslog/actions)|

## [Context](#context)

This role is part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-spamassassin/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/robertdebock):

|container|tags|
|---------|----|
|[Alpine](https://hub.docker.com/r/robertdebock/alpine)|all|
|[EL](https://hub.docker.com/r/robertdebock/enterpriselinux)|all|
|[Debian](https://hub.docker.com/r/robertdebock/debian)|all|
|[Fedora](https://hub.docker.com/r/robertdebock/fedora)|all|
|[Ubuntu](https://hub.docker.com/r/robertdebock/ubuntu)|all|

The minimum version of Ansible required is 2.12, tests have been done on:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them on [GitHub](https://github.com/buluma/ansible-role-spamassassin/issues).

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-spamassassin/blob/master/LICENSE).

## [Author Information](#author-information)

[buluma](https://buluma.github.io/)
