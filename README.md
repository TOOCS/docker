[![Build Status](https://travis-ci.org/FlorianKempenich/docker.svg?branch=master)](https://travis-ci.org/FlorianKempenich/ansible-role-docker) [![Ansible Role](https://img.shields.io/ansible/role/22557.svg)](https://galaxy.ansible.com/FlorianKempenich/docker)

# Ansible role: `docker`

Install Docker on Ubuntu. And optionally `docker-compose` and `docker-machine`.
Also sets up completion for `zsh`

## Requirements

This role is only working on Ubuntu / Debian.

## Role Variables

* `docker_compose_version`: Format '0.13.0'
* `docker_machine_version`: Format '1.17.0'

## Example Playbook
>TODO: Include examples with:
>
>* variable set / not set
>* docker compose (include role / tasks from)
>

Here is an example playbook using this Role:

    - hosts: sandbox
      roles:
         - { role: FlorianKempenich.docker, x: 42 } TODO

License
-------

MIT

Author Information
------------------

Find out more about my work: [Florian Kempenich](https://floriankempenich.com)
