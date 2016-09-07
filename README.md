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
- hosts: 'openstack-gpu-servers'
  sudo: true
  roles:
    - role: 'ryanolson.nvidia-docker'
      sudo: true
```

Ubuntu 14.04
------------

[`bootstrap.sh` is a script for 14.04 instances](https://github.com/ryanolson/bootstrap/blob/master/bootstrap.sh) that installs Docker and nvidia-docker.


Ubuntu 16.04
------------

You might have you install `python2.7` on 16.04 instances.

```yaml
- hosts: openstack-gpu-servers
  sudo: true
  gather_facts: False
  tasks:
    - name: apt-get update
      raw: apt-get update -qq
    - name: Install python 2.7
      raw: apt-get install -qq python2.7
```

Then specify the `python2.7` exectuble on the host:

```yaml
- hosts: openstack-gpu-servers
  sudo: true
  vars:
    ansible_python_interpreter: /usr/bin/python2.7
  roles:
    - role: 'ryanolson.nvidia-docker'
      sudo: true
```
