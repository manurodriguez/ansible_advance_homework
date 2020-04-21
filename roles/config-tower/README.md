Role Name
=========

This role is trigged by `site-config-tower.yml` playbook to create job templates and workflow
templates in Tower via the tower-cli or tower ansible modules


Requirements
------------

- Only Ansible core modules are used in this role
- Tested on Ansible 2.7 and above

Role Variables
--------------

See roles/config-tower/vars/main.yml 

Dependencies
------------

Role setup-workstation is required to run first to setup workstation as a tower isolated node.

Example Playbook
----------------

File: site-config-tower.yml
```
- hosts: localhost
  gather_facts: false 
  become: yes 
  roles:
    - config-tower
```

Then run:
```
[bastion]$ sudo -i
[bastion]# cd ansible_advance_homework
[bastion]# TOWER_GUID=<Ansible Tower Homework GUID from mail>
[bastion]# OSP_GUID=<Openstack for Ansible GUID from mail>
[bastion]# OPENTLC_LOGIN=<username-company.com>
[bastion]# OPENTLC_PASSWORD=<your openlc account password>
[bastion]# GITHUB_REPO=https://github.com/manurodriguez/ansible_advance_homework
[bastion]# JQ_REPO_BASE=http://www.opentlc.com/download/ansible_bootcamp
[bastion]# REGION=<enter region name example us-east-1>
[bastion]# RH_MAIL_ID=<your mail id for dynamic inventory tag>
[bastion]# ansible-playbook site-config-tower.yml -e tower_GUID=${TOWER_GUID} \
 -e osp_GUID=${OSP_GUID} -e opentlc_login=${OPENTLC_LOGIN} -e path_to_opentlc_key=/root/.ssh/mykey.pem \
 -e param_repo_base=${JQ_REPO_BASE} -e opentlc_password=${OPENTLC_PASSWORD} -e REGION_NAME=${REGION} \ 
 -e EMAIL=${RH_MAIL_ID} -e github_repo=${GITHUB_REPO} 
```

License
-------

BSD

Author Information
------------------

Manuel Rodriguez
