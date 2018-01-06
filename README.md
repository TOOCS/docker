[![Build Status](https://travis-ci.org/FlorianKempenich/ansible-role-docker.svg?branch=master)](https://travis-ci.org/FlorianKempenich/ansible-role-docker) [![Ansible Role](https://img.shields.io/ansible/role/22817.svg)](https://galaxy.ansible.com/FlorianKempenich/docker)

# Ansible role: `docker`
Install Docker on Ubuntu. And optionally `docker-compose` and `docker-machine`.
Also sets up completion for `zsh`

## Requirements
This role is only working on Ubuntu / Debian.

## Role Variables
The base version of the playbook will install the latest version of `docker-ce`. 

When installing `docker-compose` and/or `docker-machine` it is possible to specify the exact version to use:

* `docker_compose_version`: Eg. '1.17.0'
* `docker_machine_version`: Eg. '0.13.0'

## Example Playbook
To install only install `docker`:

    - hosts: sandbox
      roles:
         - FlorianKempenich.docker

To install `docker-compose` / `docker-machine`:

    - hosts: sandbox
      tasks:
        - include_role:
            name: FlorianKempenich.docker
            tasks_from: dockercompose.yml
        - include_role:
            name: FlorianKempenich.docker
            tasks_from: dockermachine.yml

To install a specific version of `docker-compose` / `docker-machine`:

    - hosts: sandbox
      tasks:
        - include_role:
            name: FlorianKempenich.docker
            tasks_from: dockercompose.yml
          vars:
            docker_compose_version: '1.17.0'


## License
MIT

## Author Information
Find out more about my work: [Florian Kempenich](https://floriankempenich.com)
