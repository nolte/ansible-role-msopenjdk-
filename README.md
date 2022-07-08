Ansible Role MSOpenJDK
=========

[![molecule e2e](https://github.com/nolte/ansible-role-msopenjdk/workflows/molecule%20e2e/badge.svg)](https://github.com/nolte/ansible-role-msopenjdk/actions?query=workflow%3A%22molecule+e2e%22) [![](https://img.shields.io/github/release/nolte/ansible-role-msopenjdk.svg)](https://github.com/nolte/ansible-role-msopenjdk) [![Install from Ansible Galaxy](https://img.shields.io/badge/role-nolte.msopenjdk-blue.svg)](https://galaxy.ansible.com/nolte/msopenjdk)

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

By default we install a jdk 16, you can change this by edit the `jdk_used_version` variable possible Values are (`11` and `16`).

### Role Parameters 

| Value               | Default                                                                                       | Description                                                                   |
|---------------------|-----------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------|
| `jdk_used_version`  | `17`                                                                                          | Used JDk Version, supported Values are `11`,`16` and `17`.                         |
| `archiveFolderName` | `{{ jdk_versions[_jdk_used_version].archiveFolderName }}`                                     | Folder Name inside the Archive, used for build the Link to the java binaries. |
| `downloadUrl`       | `https://aka.ms/download-jdk/{{ jdk_versions[_jdk_used_version].archiveName }}`               | Download Url for the JDK Archive.                                             |
| `checksumUrl`       | `https://aka.ms/download-jdk/{{ jdk_versions[_jdk_used_version].archiveName }}.sha256sum.txt` | Text file with `sha256sum` informations.                                      |

## Development

For development and testing we use [molecule](https://molecule.readthedocs.io/en/latest/) in combination with docker.

```sh

# for install jdk 11 at molecule run
export MOLECULE_JDK_USED_VERSION="11"

molecule test

```

## Links

* Used at [nolte/ansible-minecraft](https://github.com/nolte/ansible-minecraft).
