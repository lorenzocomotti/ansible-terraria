Ansible role: Terraria Server

[![Build Status](https://travis-ci.org/lorenzocomotti/ansible-role-terrariai.svg?branch=master)](https://travis-ci.org/lorenzocomotti/ansible-role-terraria)
[![Galaxy](https://img.shields.io/badge/galaxy-lorenzocomotti.ansible--role--terraria-blue.svg?style=flat-square)](https://galaxy.ansible.com/lorenzocomotti/ansible-role-terraria)

Install your Terraira server in your Ubuntu server
This palybook automatically installs the server, configures the firewall, and integrates management with systemd.<br>

## Requirements

This role requires Ansible 2.4 or higher.

## Role Variables

The role defines its variables in `defaults/main.yml`:

## Varibles definitition

|VARIABLE|DESCRIPTION|DEFAULT VALUE|
|--------|-----------|-------------|
|world|world file path|"/var/terraria-worlds/myworld.wld"|
|maxplayers|max player in the server|8|
|password|password of server|terraria| 
|Motd|Message of the day|"Welcome!"|
|world_size|World size is specified by: 1(small), 2(medium), and 3(large)|1|
|difficulty|Sets world difficulty when using -autocreate. Options: 0(normal), 1(expert)|0|
|worldname|world name|world|
|security|Adds additional cheat protection|1|
|worldpath|worlds directory path|/var/terraria-worlds|
|language|language|en/US|

More information here: [https://terraria.gamepedia.com/Server](https://terraria.gamepedia.com/Server)

## Example Playbook

Run with default vars:

```
    ---

    - name: install terraria server
      hosts: all
      tags: master
      roles:
        - role: terraria server
```

## Testing

Tests are performed using [Molecule](http://molecule.readthedocs.org/en/latest/).

Install Molecule or use `docker-compose run --rm molecule` to run a local Docker container, based on the [enterclousuite/molecule](https://hub.docker.com/r/fminzoni/molecule/) project, from where you can use `molecule`.

1. Run `molecule create` to start the target Docker container on your local engine.  
2. Use `molecule login` to log in to the running container.  
3. Edit the role files.  
4. Add other required roles (external) in the molecule/default/requirements.yml file.  
5. Edit the molecule/default/playbook.yml.  
6. Define infra tests under the molecule/default/tests folder using the goos verifier.  
7. When ready, use `molecule converge` to run the Ansible Playbook and `molecule verify` to execute the test suite.  
Note that the converge process starts performing a syntax check of the role.  
Destroy the Docker container with the command `molecule destroy`.   

To run all the steps with just one command, run `molecule test`. 
