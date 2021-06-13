Ansible Role MSOpenJDK
=========

[![molecule e2e](https://github.com/nolte/ansible-role-msopenjdk/workflows/molecule%20e2e/badge.svg)](https://github.com/nolte/ansible-role-msopenjdk/actions?query=workflow%3A%22molecule+e2e%22) [![](https://img.shields.io/github/release/nolte/ansible-role-msopenjdk.svg)](https://github.com/nolte/ansible-role-msopenjdk)

---

Install and configure [microsoft openjdk](https://docs.microsoft.com/de-de/java/openjdk/install) to host. This role will be download the openjdk archive, and place it to the local filesystem.

## Install

```
ansible-galaxy install nolte.msopenjdk
```

or add this to your ``requirements.yml``

```
- name: nolte.msopenjdk
```

and execute ``ansible-galaxy install -r requirements.yml``

## Usage

```
- hosts: all
  roles:
     - { role: nolte.msopenjdk }
```
