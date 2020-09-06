# Ansible repository with roles and playbooks that can be used to set up a Ubuntu 20.04 PC
## Current Installations
* [Terminator](https://terminator-gtk3.readthedocs.io/en/latest/)
* A Python [virtualenv](https://docs.python.org/3/library/venv.html) called "mypy3"
* [Docker](https://docs.docker.com/engine/) & [docker-compose 1.26.2](https://docs.docker.com/compose/)
* [ROCm](https://rocmdocs.amd.com/en/latest/Installation_Guide/Installation-Guide.html#software-stack-for-amd-gpu)

**Note:** This repo is still work in progress, so more roles might be added.

## Prerequisites
* Ansible
  * Install first a virtual env, source it afterwards to activate it and finally install Ansible
    * `sudo apt install python3-venv`
    * `mkdir $HOME/.envs && python3 -m venv $HOME/.envs/ansible-env`
    * `source $HOME/.envs/ansible-env/bin/activate`
    * `pip install ansible`
 * Git
   * `sudo apt install git`

## How to use this repo

1. Source your ansible environment: `source $HOME/.envs/ansible-env/bin/activate`
2. Clone repo: `git clone https://github.com/reinka/config_ubuntu.git`
3. Change directory and run the playbook locally (make sure to substitute `ansible_sudo_pass` with your
 sudo password:
```shell script
$ cd config_ubuntu 
$ ansible-playbook --connection=local --inventory 127.0.0.1, \ 
  playbooks/execute_roles.yml -e ansible_sudo_pass='****'
```
