create_db_service
=================

This role creates a couple of systemd services to startup and shutdow the Oracle databse service and its listener. As the scripts {{ oracle_home }}/bin/dbstart and {{ oracle_home }}/bin/dbshut are used. The /etc/oratab file is modified to allow the usage of these scripts.

Requirements
------------

An Oracle database has been installed using the role install_oracle_db.

Role Variables
--------------

#### cdbs_service_path: /usr/lib/systemd/system
The path used to create the service files used to manage the database and its listener as services.

#### oracle_base
The oracle base path used by the service.

#### oracle_home
The Oracle Home used by the service.

#### sid
The Oracle SID used by the service.

Dependencies
------------

Before running using this, the following roles must be executed.

1. os_settings
1. install_oracle_db

This role depens on some variables located at ANSIBLE-ORACLEDB/inventories/dev/group_vars/oracledb_vars.yml

Example Playbook
----------------

The following example shows how to use this role. It needs root as this will create two services one for the database and the other for the listener.

    - hosts: database
      remote_user: oracle
      become: yes
      become_user: root
      tasks:
        # Here we will call the role to create Linux Services for Oracle database
      - include_role:
          name: create_db_service

License
-------

BSD

Author Information
------------------

[RSCC](https://www.linkedin.com/in/raul-castillo-11051980/)