Role Name
=========

This role installs tomcat and setup a basic webpage on port 8080 on RHEL7 instances

Requirements
------------

- Only Ansible core modules are used in this role
- No special python dependencies
- Tested on Ansible 2.7 and above

Role Variables
--------------

- Package name variable as provided by repositories:
app_name: tomcat

- Service name variable as managed by systemd: 
app_package: tomcat

Dependencies
------------

base-config role is required to run first to setup repositories and access to packages
You might need to use in combination with a role to generate the openstack inventory as role `osp-facts`

Example Playbook
----------------

  hosts: apps
  become: yes
  roles:
    - {name: apps-tier, tags: [apps, tomcat]}

License
-------

BSD

Author Information
------------------

Manuel Rodriguez
