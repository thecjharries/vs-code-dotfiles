# `vs-code-dotfiles`

[![License: Apache 2.0](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)  [![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/) [![Check the NOTICE](https://img.shields.io/badge/Check%20the-NOTICE-420C3B.svg)](./NOTICE)

This repo is a simple way for me to spin up all the stuff I want to use in VS Code. At the moment it only includes Ubuntu setup because I haven't deployed VS Code anywhere else yet.

## Dependencies

### Ansible

Find the most current installation instructions [in their docs](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html).

Current Ubuntu 20.04 installation instructions are presented below. The docs mention [an Ansible PPA](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-ansible-on-ubuntu) but it does not currently support `focal`.

```shell
sudo apt update
sudo apt install ansible
```
