Role Name
=========

This role installs, initializes and starts postgresql on RHEL7 instances

Requirements
------------

- Only Ansible core modules are used in this role
- No special python dependencies
- Tested on Ansible 2.7 and above

Role Variables
--------------

- Package name variable as provided by repositories:
appdb_name: postgresql

- Service name variable as managed by systemd: 
appdb_package: postgresql-server

Dependencies
------------

base-config role is required to run first to setup repositories and access to packages

Example Playbook
----------------

  hosts: appdbs
  become: yes
  roles:
    - {name: db-tier, tags: [dbs, postgres]}

License
-------

BSD

Author Information
------------------

Manuel Rodriguez
