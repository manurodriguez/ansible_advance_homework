Role Name
=========

This role configures workstation server as an isolated node for tower to run playbooks
it also creates osp networks, router, SG, flavor, and ssh keypair through the workstation node

Requirements
------------

- Tested on Ansible 2.7 and above
- python3, python-pip3, and openstacksdk latest for openstack tasks to run. These are installed by this role.

Role Variables
--------------

See roles/setup-workstation/vars/main.yml for full details of the openstack cloud variables

This playbook uses vault repo_vars.yml which contains repository variables. This repo
provides python3 packages easy to install via yum. It is on a vault to protect URL.

```
tower_repo:
  - name: "rhel-7-server-rpms-tower"
    description: "Red Hat Enterprise Linux 7 Tower"
    baseurl: http://mirror-to-download-python-packages.com/repos/rhel-7-server-rpms"
```

Dependencies
------------

This role has no dependecines, but it triggers playbook site-install-isolated-node.yml

Example Playbook
----------------

File: site-setup-workstation.yml
```
- hosts: localhost
  tasks:
  - name: Create workstation inventory
    add_host:
       name: "workstation-{{OSP_GUID}}.rhpds.opentlc.com"
       group: workstation


- hosts: workstation
  become: yes
  roles:
    - setup-workstation

- import_playbook: site-install-isolated-node.yml 
```

Then run:
```
[bastion]$ sudo -i
[bastion]# cd ansible_advance_homework
[bastion]# OSP_GUID=<Openstack for Ansible GUID from mail>
[bastion]# ansible-playbook site-setup-workstation.yml -e OSP_GUID=${OSP_GUID} -e @repo_vars.yml --private-key=/root/.ssh/mykey.pem -u <username-company.com> --ask-vault-pass
```

License
-------

BSD

Author Information
------------------

Manuel Rodriguez
