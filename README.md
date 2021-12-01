# Developer box setup via Ansible

![CI](https://github.com/baztian/ansible-devbox/workflows/CI/badge.svg)

Ansible playbook whose aim is to save time setting up a Ubuntu based distribution like Ubuntu or Linux Mint for software development purposes.

## Prepare ansible installation

    sudo -s
    apt-add-repository -y ppa:ansible/ansible
    apt update
    apt install -y ansible git
    cat > /etc/ansible/ansible.cfg <<HERE

    [defaults]
    interpreter_python = /usr/bin/python3
    nocows = 1
    HERE
    exit

## Usage

Install on local machine using `ansible-pull` (without the need checking out this repository).

    ansible-pull -U https://github.com/baztian/ansible-devbox.git -i local playbook.yml -K

Alternatively install after checking out this repository on local machine using `ansible`.

    ansible-playbook playbook.yml -i local -K

Force upgrade required ansible roles.

    ansible-galaxy install -f -r requirements.yml

## Role dependencies

This playbook depends on several roles.

|Galaxy Role|Github Role|
| --------- | --------- |
| [baztian.apt_upgrade](https://galaxy.ansible.com/baztian/apt_upgrade) | [![CI](https://github.com/baztian/ansible-apt-upgrade/workflows/CI/badge.svg)](https://github.com/baztian/ansible-apt-upgrade) |
| [baztian.git](https://galaxy.ansible.com/baztian/git) | [![CI](https://github.com/baztian/ansible-git/workflows/CI/badge.svg)](https://github.com/baztian/ansible-git) |
| [baztian.asdf](https://galaxy.ansible.com/baztian/asdf) | [![CI](https://github.com/baztian/ansible-asdf/workflows/CI/badge.svg)](https://github.com/baztian/ansible-asdf) |
| [baztian.docker](https://galaxy.ansible.com/baztian/docker) | [![CI](https://github.com/baztian/ansible-docker/workflows/CI/badge.svg)](https://github.com/baztian/ansible-docker) |
| [baztian.vscode](https://galaxy.ansible.com/baztian/vscode) | [![CI](https://github.com/baztian/ansible-vscode/workflows/CI/badge.svg)](https://github.com/baztian/ansible-vscode) |
| [baztian.python](https://galaxy.ansible.com/baztian/python) | [![CI](https://github.com/baztian/ansible-python/workflows/CI/badge.svg)](https://github.com/baztian/ansible-python) |
| [baztian.pip_venv](https://galaxy.ansible.com/baztian/pip_venv) | [![CI](https://github.com/baztian/ansible-pip-venv/workflows/CI/badge.svg)](https://github.com/baztian/ansible-pip-venv) |
| [baztian.adr_tools](https://galaxy.ansible.com/baztian/adr_tools) | [![CI](https://github.com/baztian/ansible-adr-tools/workflows/CI/badge.svg)](https://github.com/baztian/ansible-adr-tools) |
| [baztian.dev_tools](https://galaxy.ansible.com/baztian/dev_tools) | [![CI](https://github.com/baztian/ansible-dev-tools/workflows/CI/badge.svg)](https://github.com/baztian/ansible-dev-tools) |
| [baztian.java](https://galaxy.ansible.com/baztian/java) | [![CI](https://github.com/baztian/ansible-java/workflows/CI/badge.svg)](https://github.com/baztian/ansible-java) |
| [baztian.aws](https://galaxy.ansible.com/baztian/aws) | [![CI](https://github.com/baztian/ansible-aws/workflows/CI/badge.svg)](https://github.com/baztian/ansible-aws) |
| [baztian.keepass](https://galaxy.ansible.com/baztian/keepass) | [![CI](https://github.com/baztian/ansible-keepass/workflows/CI/badge.svg)](https://github.com/baztian/ansible-keepass) |
| [baztian.jetbrains_toolbox](https://galaxy.ansible.com/baztian/jetbrains_toolbox) | [![CI](https://github.com/baztian/ansible-jetbrains-toolbox/workflows/CI/badge.svg)](https://github.com/baztian/ansible-jetbrains-toolbox) |
| [baztian.js](https://galaxy.ansible.com/baztian/js) | [![CI](https://github.com/baztian/ansible-js/workflows/CI/badge.svg)](https://github.com/baztian/ansible-js) |
| [baztian.other_installs](https://galaxy.ansible.com/baztian/other_installs) | [![CI](https://github.com/baztian/ansible-other-installs/workflows/CI/badge.svg)](https://github.com/baztian/ansible-other-installs) |
| [baztian.buildnotify](https://galaxy.ansible.com/baztian/buildnotify) | [![CI](https://github.com/baztian/ansible-buildnotify/workflows/CI/badge.svg)](https://github.com/baztian/ansible-buildnotify) |
| [baztian.mob](https://galaxy.ansible.com/baztian/mob) | [![CI](https://github.com/baztian/ansible-mob/workflows/CI/badge.svg)](https://github.com/baztian/ansible-mob) |
| [baztian.adr_tools](https://galaxy.ansible.com/baztian/adr_tools) | [![CI](https://github.com/baztian/ansible-adr-tools/workflows/CI/badge.svg)](https://github.com/baztian/ansible-adr-tools) |

## Other suggested roles

To install any of the below roles do the following steps (replace ROLENAME with the desired Ansible role name):

    ansible-galaxy install baztian.ROLENAME
    ansible-play-role-local baztian.ROLENAME -K -b

|Galaxy Role|Github Role|
| --------- | --------- |
| [baztian.xfce](https://galaxy.ansible.com/baztian/xfce) | [![CI](https://github.com/baztian/ansible-xfce/workflows/CI/badge.svg)](https://github.com/baztian/ansible-xfce) |
| [baztian.emacs](https://galaxy.ansible.com/baztian/emacs) | [![CI](https://github.com/baztian/ansible-emacs/workflows/CI/badge.svg)](https://github.com/baztian/ansible-emacs) |
| [baztian.gocryptfs](https://galaxy.ansible.com/baztian/gocryptfs) | [![CI](https://github.com/baztian/ansible-gocryptfs/workflows/CI/badge.svg)](https://github.com/baztian/ansible-gocryptfs) |
| [baztian.jython](https://galaxy.ansible.com/baztian/jython) | [![CI](https://github.com/baztian/ansible-jython/workflows/CI/badge.svg)](https://github.com/baztian/ansible-jython) |
| [baztian.multimedia](https://galaxy.ansible.com/baztian/multimedia) | [![CI](https://github.com/baztian/ansible-multimedia/workflows/CI/badge.svg)](https://github.com/baztian/ansible-multimedia) |
| [baztian.squeezeplay](https://galaxy.ansible.com/baztian/squeezeplay) | [![CI](https://github.com/baztian/ansible-squeezeplay/workflows/CI/badge.svg)](https://github.com/baztian/ansible-squeezeplay) |
| [baztian.skype](https://galaxy.ansible.com/baztian/skype) | [![CI](https://github.com/baztian/ansible-skype/workflows/CI/badge.svg)](https://github.com/baztian/ansible-skype) |
| [baztian.calibre](https://galaxy.ansible.com/baztian/calibre) | [![CI](https://github.com/baztian/ansible-calibre/workflows/CI/badge.svg)](https://github.com/baztian/ansible-calibre) |
| [baztian.joplin](https://galaxy.ansible.com/baztian/joplin) | [![CI](https://github.com/baztian/ansible-joplin/workflows/CI/badge.svg)](https://github.com/baztian/ansible-joplin) |
| [baztian.salesforce](https://galaxy.ansible.com/baztian/salesforce) | [![CI](https://github.com/baztian/ansible-salesforce/workflows/CI/badge.svg)](https://github.com/baztian/ansible-salesforce) |
| [baztian.borgbackup](https://galaxy.ansible.com/baztian/borgbackup) | [![CI](https://github.com/baztian/ansible-borgbackup/workflows/CI/badge.svg)](https://github.com/baztian/ansible-borgbackup) |
| [baztian.signal](https://galaxy.ansible.com/baztian/signal) | [![CI](https://github.com/baztian/ansible-signal/workflows/CI/badge.svg)](https://github.com/baztian/ansible-signal) |
