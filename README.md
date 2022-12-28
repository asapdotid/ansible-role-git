<p align="center"> <img src="https://user-images.githubusercontent.com/34257858/129839002-15e3f2c7-3f75-46d4-afae-0fd207d7fdde.png" width="100" height="100"></p>

<h1 align="center">
    Ansible Role Git
</h1>

<p align="center" style="font-size: 1.2rem;">
    Installs Git, a distributed version control system, on any RHEL/CentOS or Debian/Ubuntu Linux system.
    Base project [Jeff Geerling](https://www.jeffgeerling.com/)
</p>

<p align="center">

<a href="https://www.ansible.com">
  <img src="https://img.shields.io/badge/Ansible-2.10-green?style=flat&logo=ansible" alt="Ansible">
</a>
<a href="LICENSE.md">
  <img src="https://img.shields.io/badge/License-MIT-blue.svg" alt="Licence">
</a>
<a href="https://ubuntu.com/">
  <img src="https://img.shields.io/badge/ubuntu-20.x-orange?style=flat&logo=ubuntu" alt="Distribution">
</a>
<a href="https://www.centos.org/">
  <img src="https://img.shields.io/badge/CentOS-8-green?style=flat&logo=centos" alt="Distribution">
</a>

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    workspace: /tmp/git-sources

The most current stable version of Git for Debian.

    git_repository: "ppa:git-core/ppa"

This variable, a well as `git_packages`, will be used to install git via a particular `yum` repo if `git_install_from_source` is false (CentOS only). Any additional repositories you have installed that you would like to use for a newer/different Git version.

    git_packages:
      - git

The specific Git packages that will be installed. By default, only `git` is installed, but you could add additional git-related packages like `git-svn` if desired.

    git_install_from_source: false
    git_install_path: "/usr"
    git_version: "2.38.2"

Whether to install Git from source; if set to `true`, `git_version` is required and will be used to install a particular version of git (see all available versions here: https://mirrors.edge.kernel.org/pub/software/scm/git/), and `git_install_path` defines where git should be installed.

    git_install_from_source_force_update: false

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
