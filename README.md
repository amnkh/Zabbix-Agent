# Zabbix Agent Playbook

[![Build Status](https://travis-ci.org/danitfk/Zabbix-Agent.svg?branch=master)](https://travis-ci.org/danitfk/Zabbix-Agent)

A simple Ansible playbook to install zabbix agent on server.

  - Add Zabbix release repository (v3.4)
  - Install latest Zabbix agent
  - Enable zabbix Agent at boot

# Supported OS:

- Ubuntu 14.04 Trusty LTS
- Ubuntu 16.04 Xenial LTS
- Ubuntu 18.04 Bionic LTS
- Debian 7 Wheezy
- Debian 8 Jessie
- Debian 9 Stretch
- CentOS/Redhat 6
- CentOS/Redhat 7

# To Do:
- Add rule into Firewall (ufw)

# How to use:
Create a playbook then run the role.
Example playbook (called main.yml, keep in mind create main.yml one directory before Zabbix-Agent repo):
```
---
- hosts: 192.168.1.2
  become: yes
  become_method: sudo
  roles:
       - { role: Zabbix-Agent, zabbix_agent_server: 192.168.1.1 }

```
then clone the repo:
```
git clone https://github.com/danitfk/Zabbix-Agent.git
```
Before run the playbook, change some variables in main.yaml.
```
zabbix_agent_server: ZABBIX-SERVER-IP
```
after changing localhost to desired IP of Zabbix Server / Zabbix proxy then run the playbook.

```
ansible-playbok main.yaml
```
![alt Ansible playbook install zabbix agent on linux server](https://github.com/danitfk/Zabbix-Agent/blob/master/screenshots/Zabbix-Agent-Ansible.png?raw=true)

