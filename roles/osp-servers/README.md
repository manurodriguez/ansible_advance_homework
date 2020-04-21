Role Name
=========

This role deploys RHEL7 instances on Openstack, and attach Floating IPs.

Requirements
------------

- Tested on Ansible 2.7 and above
- python3, python-pip3
- openstacksdk >= 0.46.0

Role Variables
--------------

See roles/osp-servers/vars/main.yml for details of instance variables

Default variables, modify if your environment has different:

```
cloud: ospcloud
int_network: int_network
ext_network: ext_network
openstack_pubkey: "ssh-rsa..."
opentlc_pubkey: "ssh-rsa ..."
```

Dependencies
------------

Roles:
- setup-workstation

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
