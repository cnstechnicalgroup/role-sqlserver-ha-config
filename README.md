Role: cnstechnicalgroup.sqlserver-ha-config
========

Ansible role install SQL Server High Availability Components and configure hosts for mirror communications

Requirements
------------

* CentOS7 
* Ubuntu Xenial Xenus


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
| sa_password           |  no      |   ---   | system administrator password for SQL Server install, required for dependency                                                                                    .  |



* If you choose to use /etc/hosts to resolve each machine that is participating in the AG, don't forget to add those ip addresses and hosts to the /etc/hosts file of the ansible server. This is necessary because the ansible server is used to run sqlcmd.  


Dependencies
------------

Depends upon [role-sqlserver-server](https://github.com/cnstechnicalgroup/role-sqlserver-server)

License
-------

GPLv2

Author Information
------------------

Created by CNS Technical Group (https://www.cnstechgroup.com/)

Documentation
------------------

Install example (https://github.com/cnstechnicalgroup/ansible-sqlserver/blob/master/documents/sqlserver-ha-config.md)


Examples
--------

```yaml
---
- name: cnstechnicalgroup.sqlserver-ha-config role 
  hosts: dbservers
  sudo: yes
  roles: 
    - cnstechnicalgroup.sqlserver-ha-config
  gather_facts: yes
  environment:
   SA_PASSWORD: "{{sa_password}}"
   ACCEPT_EULA: "Y"
```
