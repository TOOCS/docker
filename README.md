[![Build Status](https://travis-ci.org/TOOCS/docker.svg?branch=master)](https://travis-ci.org/TOOCS/docker) [![Ansible Role](https://img.shields.io/ansible/role/36155.svg)](https://galaxy.ansible.com/FlorianKempenich/toocs_docker)

# TOOCS / Ansible Role: `FlorianKempenich.toocs_docker`
Install Docker on Ubuntu. And optionally `docker-compose` and `docker-machine`.
Also sets up completion for `zsh`

> ### TOOCS?
> TOOCS - The Opinionated One-Click Setups are a set of tools / ansible roles designed to setup a system in one click. They are a simple, reliable, way to setup a given tool. You can use them as is, or, inspecting their code, as a tutorial to follow step by step.
> 
> They are, as their name suggests, opinionated: while they guarantee to setup the given tool in one click, they do **not** guarantee consistency in _how_ they achieve it, new releases might introduce breaking changes.  
> Read the code and make sure you understand what's happening!

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
         - FlorianKempenich.toocs_docker

To install `docker-compose` / `docker-machine`:

    - hosts: sandbox
      tasks:
        - include_role:
            name: FlorianKempenich.toocs_docker
            tasks_from: dockercompose.yml
        - include_role:
            name: FlorianKempenich.toocs_docker
            tasks_from: dockermachine.yml

To install a specific version of `docker-compose` / `docker-machine`:

    - hosts: sandbox
      tasks:
        - include_role:
            name: FlorianKempenich.toocs_docker
            tasks_from: dockercompose.yml
          vars:
            docker_compose_version: '1.17.0'


## License
MIT

## Author Information
Find out more about my work: [Florian Kempenich](https://floriankempenich.com)
