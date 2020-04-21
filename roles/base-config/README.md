Role Name
=========

This role setups yum repositories on RHEL7 instances

Requirements
------------

- Only Ansible core modules are used in this role
- No special python dependencies
- Tested on Ansible 2.7 and above

Role Variables
--------------

The following variables need to be defined in roles/base-config/vars/vault.yml they are protected.
You need to provide a value of URL, for example: `http://my-internal-mirror/repos/rhel-7-server-rpms`

- vault_rhel_7_server_rpms_baseurl:
- vault_rhel_7_server_rh_common_rpms_baseurl: 
- vault_rhel_7_server_extras_rpms_baseurl: 
- vault_rhel_7_server_optional_rpms_baseurl: 

The values above provide values to other variables that you can view with a text search like grep

repositories:
  - name: "rhel-7-server-rpms"
    description: "Red Hat Enterprise Linux 7"
    baseurl: "{{ vault_rhel_7_server_rpms_baseurl }}"

Dependencies
------------

This role does not have dependencies

Example Playbook
----------------

  hosts: apps,frontends,appdbs
  become: yes
  vars_files:
    - roles/base-config/vars/vault.yml
  roles:
    - {name: base-config, tags: base-config}

License
-------

BSD

Author Information
------------------

Manuel Rodriguez
