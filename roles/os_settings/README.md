os_settings
===========

The goal of this roles is to set the Linux (CentOS in this case) Operating System v7 according to the requirements provided by Oracle to install an Oracle Fusion Middleware 12.2.1.4

Requirements
------------

You will need a machine with Centos 7 and do not forget to execute this.

Role Variables
--------------
os_packages, a list of OS packages installed on target(s) machines.
limits, a dictionary, which represents the soft and hard limits for processes and files to be set before installing Oracle database.

Dependencies
------------
At this moment this roles does not depend on other roles or external variables.

Example Playbook
----------------

This roles can be executed as is shown below.

      - hosts: soa
        remote_user: oracle
        tasks:
         - include_role:
            name: os_settings

License
-------

BSD

Author Information
------------------

[RSCC](https://www.linkedin.com/in/raul-castillo-11051980/)