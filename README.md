nvidia-docker
=============

This Ansible role enables people to install the latest version of docker
and nvidia-docker on an Ubuntu 14.04 or 16.04 LTS system.


Requirements
------------

This role will only work on an Ubuntu 14.04 or 16.04 LTS system.


Examples
--------

Install this module from Ansible Galaxy into the './roles' directory:

```bash
ansible-galaxy install ryanolson.nvidia-docker -p ./roles
```

Use it in a playbook as follows:

```yaml
- hosts: 'servers'
  roles:
    - role: 'ryanolson.nvidia-docker'
      sudo: true
```
