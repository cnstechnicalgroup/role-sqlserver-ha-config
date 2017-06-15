Role: role.sqlserver-ha-config
========

Ansible role install SQL Server High Availability Components and configure hosts for mirror communications

Requirements
------------

* CentOS7 

Role Variables
--------------

In the current version, you can specify the following variables:

| Name                  | Default |                                                              |
|-----------------------|---------|--------------------------------------------------------------|
| use_hosts_file        |   ---   | use /etc/hosts file for DNS resolution               .  |
| primary_host_ip       |   ---   | IP Address for the principal server in Always On     .  |
| secondary_host_ip     |   ---   | IP Address for the replica server in Always On       .  |


Dependencies
------------

Depends upon role-sqlserver-server

License
-------

GPLv2

Author Information
------------------

Created by CNS Technical Group (https://www.cnstechgroup.com/)

Examples
--------

```yaml
---
- name: role.sqlserver-ha-config role 
  hosts: dbservers
  sudo: yes
  roles: 
  - cns.role-sqlserver-ha-config
  gather_facts: yes

```
