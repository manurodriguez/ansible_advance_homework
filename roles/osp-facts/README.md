Role Name
=========

This role fetches Openstack instances public IP addresses and metadata to generate inventory.

Requirements
------------

- Tested on Ansible 2.7 and above
- python3, python-pip3
- openstacksdk >= 0.46.0

Role Variables
--------------

`cloud: ospcloud`

Dependencies
------------

Roles:
- setup-workstation
- osp-servers

Example Playbook
----------------

File: site-osp-instances.yml
```
- hosts: workstation
  gather_facts: false
  become: yes
  roles:
    - osp-servers
  vars:
    ansible_python_interpreter: /usr/bin/python3
```

License
-------

BSD

Author Information
------------------

Manuel Rodriguez
