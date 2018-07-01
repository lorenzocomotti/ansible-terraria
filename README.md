[![Galaxy](https://img.shields.io/badge/galaxy-lorenzocomotti.ansible--role--terraria-blue.svg?style=flat-square)](https://galaxy.ansible.com/lorenzocomotti/ansible-role-terraria)

# Terraria-server-Ansible

Install your Terraira server in your centos Machine with Ansible
This palybook automatically installs the server, configures the firewall, and integrates management with systemd.<br>
The server version is 1.353

# How to Install Terraria Server
1- Run "yum update"<br>
2- Run "yum install epel-release"<br>
3- Run "yum install Ansible"<br>
4- Run "Ansible-playbook Defaults/mail.yml"<br>

# How Custom your server before installation
you can change the server settings in the following file: "Defautls/group_vars/all" <br>
before executing playbook Ansible
