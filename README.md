Role Name
=========

vsftpd

[![Build Status](https://travis-ci.org/cmihai-ansible/vsftpd.svg?branch=master)](https://travis-ci.org/cmihai-ansible/vsftpd)

Ansible galaxy:
---------------

[https://galaxy.ansible.com/crivetimihai/vsftpd](https://galaxy.ansible.com/crivetimihai/vsftpd)

```bash
ansible-galaxy install crivetimihai.vsftpd
```

Requirements
------------

- For RHEL, a Red Hat subscription or functional local repository.

Role Variables
--------------

```yaml
vsftpd_enable_service: true
vsftpd_copy_templates: true
vsftpd_firewall_configure: true
vsftpd_firewall_rules:
  - service: ftp
```

Dependencies
------------

- For Red Hat, subscription-manager.

Example Playbook
----------------

```yaml
---
- name: Install vsftpd on localhost
  hosts:
    - localhost
  connection: local

  tasks:
    - name: vsftpd is configured
      import_role:
        name: crivetimihai.vsftpd
      vars:
        vsftpd_enable_service: true
        vsftpd_copy_templates: true
        vsftpd_firewall_configure: true
        vsftpd_firewall_rules:
          - service: ftp
      tags: vsftpd
```

License
-------

MIT

Author Information
------------------

- [Mihai Criveti](https://www.linkedin.com/in/crivetimihai/)
