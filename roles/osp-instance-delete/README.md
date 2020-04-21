Role Name
=========

This role deletes instances and FIPs

Requirements
------------

- Tested on Ansible 2.7 and above
- python3, python-pip3
- openstacksdk >= 0.46.0

Role Variables
--------------


Default variables, modify if your environment has different:

`cloud: ospcloud`

Dependencies
------------

Roles:
- setup-workstation

Example Playbook
----------------

File: site-osp-delete.yml
```
- hosts: workstation
  gather_facts: false
  become: yes
  roles:
    - osp-instance-delete
  vars:
    ansible_python_interpreter: /usr/bin/python3
```

License
-------

BSD

Author Information
------------------

Manuel Rodriguez
