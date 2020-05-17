os_settings
===========

The goal of this roles is to set the Linux Operating System v7 according to the requirements provided by Oracle to install an Oracle database 12.2

Requirements
------------

You will need a machine with Redhat 7.7 and do not forget to execute this.

sudo yum-config-manager --enable rhel-7-server-optional-rpms

Next time, I will automate previous step. However, beyond the way to set this, this is needed.

Role Variables
--------------
os_packages, a list of OS packages installed on target(s) machines.
sysctl_configurations, a dictionary, which represents the configurations applied on /etc/sysctl.conf before the installation of Oracle database.
limits, a dictionary, which represents the soft and hard limits for processes and files to be set before installing Oracle database.

Dependencies
------------
At this moment this roles does not depend on other roles or external variables.

Example Playbook
----------------

This roles can be executed as is shown below.

      - hosts: database
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