Role: cns.sqlserver-ha-config
========

Ansible role install SQL Server High Availability Components and configure hosts for mirror communications

Requirements
------------

* CentOS7 

Role Variables
--------------

In the current version, you can specify the following variables:

| Name                  | Optional | Default | Description                                                                                                                                                         |
|-----------------------|----------|---------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| use_hosts_file        |  yes     |   no    | Use /etc/hosts file for DNS resolution. A yes value will add an entry in /etc/hosts for the primary and secondary hosts participating in the mirror              .  |
| primary_host_ip       |  yes     |   ---   | IP Address for the principal server in Always On. This is required only if use_hosts_file is yes                                                                 .  |
| secondary_host_ip     |  yes     |   ---   | IP Address for the replica server in Always On. This is required only if use_hosts_file is yes                                                                   .  |
| primary_host_name     |  no      |   ---   | Primary host name for the server that is being mirrored (principal)                                                                                              .  |
| secondary_host_name   |  no      |   ---   | Secondary host name for the server that is mirroring (replica)                                                                                                   .  |

Dependencies
------------

Depends upon [role-sqlserver-server](https://github.com/cnstechnicalgroup/role-sqlserver-server)

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
- name: cns.sqlserver-ha-config role 
  hosts: dbservers
  sudo: yes
  roles: 
    - cns.sqlserver-ha-config
  gather_facts: yes

```
