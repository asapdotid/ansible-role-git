<p align="center"> <img src="https://user-images.githubusercontent.com/34257858/129839002-15e3f2c7-3f75-46d4-afae-0fd207d7fdde.png" width="100" height="100"></p>

<h1 align="center">
    Ansible Role Git
</h1>

<p align="center" style="font-size: 1.2rem;">
    Installs Git, a distributed version control system, on any RHEL/CentOS/Almalinux/Rocky Linux, Fedora, Debian/Ubuntu Linux system.
</p>

<p align="center">
  <a href="#">
    <img alt="GitHub tag (with filter)" src="https://img.shields.io/github/v/tag/asapdotid/ansible-role-git">
  </a>
  <a href="https://www.ansible.com">
    <img src="https://img.shields.io/badge/Ansible-2.10-green?style=flat&logo=ansible" alt="Ansible">
  </a>
  <a href="LICENSE.md">
    <img src="https://img.shields.io/badge/License-MIT-blue.svg" alt="Licence">
  </a>
</p>

Custom and inspire from [Jeff Geerling - Ansible role git](https://github.com/geerlingguy/ansible-role-git) with updates. Needed something simple and working, this did the trick for me.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

| Name                        | Default Value | Description                                                   |
| --------------------------- | ------------- | ------------------------------------------------------------- |
| `git_setup`                 | `install`     | Specify whether you want to install Git `install`/`uninstall` |
| `git_version`               | `"2.40.1"`    | The version of the Git to install                             |
| `git_install_from_source`   | `false`       | Git install from source                                       |
| `git_reinstall_from_source` | `false`       | Only applies if `git_install_from_source` is `true`           |

The most current stable version of Git for Debian.

    git_debian_repository: "ppa:git-core/ppa"

This variable, a well as `git_package`, will be used to install git via a particular `yum` repo if `git_install_from_source` is false (CentOS only). Any additional repositories you have installed that you would like to use for a newer/different Git version.

    git_install_from_source: false

Whether to install Git from source; if set to `true`, `git_version` is required and will be used to install a particular version of git (see all available versions here: https://mirrors.edge.kernel.org/pub/software/scm/git/), and `git_install_path` defines where git should be installed.

    git_reinstall_from_source: false

If git is already installed at and older version, force a new source build. Only applies if `git_install_from_source` is `true`.

## Dependencies

None.

## Example Playbook

    - hosts: servers
      roles:
        - { role: asapdotid.git }

## License

MIT / BSD

## Author Information

This Ansible Role Git was created in 2021 by [Asapdotid](https://github.com/asapdotid).
