# `vs-code-dotfiles` <!-- omit in toc --> 

[![License: Apache 2.0](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)  [![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/) [![Check the NOTICE](https://img.shields.io/badge/Check%20the-NOTICE-420C3B.svg)](./NOTICE)

This repo is a simple way for me to spin up all the stuff I want to use in VS Code. At the moment it only includes Ubuntu setup because I haven't deployed VS Code anywhere else yet.

- [Dependencies](#dependencies)
  - [Ansible](#ansible)
  - [VS Code](#vs-code)
    - [Direct](#direct)
    - [Potentially Broken](#potentially-broken)
- [Usage](#usage)

## Dependencies

### Ansible

Find the most current installation instructions [in their docs](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html).

Current Ubuntu 20.04 installation instructions are presented below. The docs mention [an Ansible PPA](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-ansible-on-ubuntu) but it does not currently support `focal`.

```shell
sudo apt update
sudo apt install ansible
```

### VS Code

#### Direct

```shell
curl -fL https://update.code.visualstudio.com/latest/linux-deb-x64/stable -o code.deb
sudo apt install -f ./code.deb
rm -rf code.deb
```

#### Potentially Broken

Snap install can have issues on newer versions of Ubuntu; direct is preferred on `20.04+` (for now).

```shell
sudo snap install --classic code
```

I could install with Ansible but that's a one-liner.


## Usage

```shell
ansible-playbook --ask-become-pass playbook.yml
```
