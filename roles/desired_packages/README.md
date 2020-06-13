# `desired_packages`

[![License: Apache 2.0](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)  [![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/) [![Check the NOTICE](https://img.shields.io/badge/Check%20the-NOTICE-420C3B.svg)](../../NOTICE)

THis currently only works with operating systems that use `aptitude`.

## Input

`desired_packages` expects a list of hashes named `packages_to_install` to be passed in.

| key | default | docs |
|---|---|---|
| `repo` | | [link](https://docs.ansible.com/ansible/latest/modules/apt_repository_module.html#parameter-repo) |
| `repo_state` | `present` | [link](https://docs.ansible.com/ansible/latest/modules/apt_repository_module.html#parameter-state) |
| `name` | | [link](https://docs.ansible.com/ansible/latest/modules/apt_module.html#parameter-name) |
| `package_state` | `present` | [link](https://docs.ansible.com/ansible/latest/modules/apt_module.html#parameter-state) |
| `install_recommends` | `no` | [link](https://docs.ansible.com/ansible/latest/modules/apt_module.html#parameter-install_recommends) |
| `force_update` | `no` | used to force a cache update both after adding the repo if defined and before installing the package |

## Action

For each element, if `repo` is defined, add the repo using `repo_state`. If `force_update` is truthy, update the cache after adding the repo.

Update the cache if it's older than 3600 seconds.

For each element, if `force_update` is truthy, update the cache. Install package `name` using `package_state`. If `install_recommends` is truthy, also install recommended packages.


## Example


```yaml
---
- hosts: localhost

  vars:
    packages_to_install:
      - name: git
        package_state: present
      - name: keepass2
        repo: ppa:jtaylor/keepass
      - name: keepass2-plugin-keeagent
        repo: ppa:dlech/keepass2-plugins

  roles:
    - role: desired_packages
```
