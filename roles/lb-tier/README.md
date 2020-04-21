Role Name
=========

This role implements haproxy on RHEL7 instances

Requirements
------------

- Only Ansible core modules are used in this role
- No special python dependencies
- Tested on Ansible 2.7 and above

Role Variables
--------------

- Package name variable as provided by repositories:
frontend_packages: haproxy

- Service name variable as managed by systemd: 
frontend_service: haproxy

Dependencies
------------

base-config role is required to run first to setup repositories and access to packages
You might need to use in combination with a role to generate the openstack inventory as role `osp-facts`

Example Playbook
----------------

  hosts: frontends
  become: yes
  roles:
    - {name: lb-tier, tags: [lbs, haproxy]}

License
-------

BSD

Author Information
------------------

Manuel Rodriguez
