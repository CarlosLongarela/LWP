Ansible Role: Apt
=========

[![Build Status](https://travis-ci.org/CarlosLongarela/ansible-role-apt.svg?branch=master)](https://travis-ci.org/CarlosLongarela/ansible-role-apt)
[![Percentage of issues still open](http://isitmaintained.com/badge/open/CarlosLongarela/ansible-role-apt.svg)](http://isitmaintained.com/project/CarlosLongarela/ansible-role-apt "Percentage of issues still open")
[![Average time to resolve an issue](http://isitmaintained.com/badge/resolution/CarlosLongarela/ansible-role-apt.svg)](http://isitmaintained.com/project/CarlosLongarela/ansible-role-apt "Average time to resolve an issue")

Basics apps installation for other roles and system administration. This role is util for a empty xenial ubuntu before execute other roles.

Requirements
------------

None.

Role Variables
--------------

    aptget_update: true
    aptget_update_cache_valid_time: 3600

    aptget_upgrade: true
    aptget_distupgrade: false

    aptget_install:
      - mc
      - nano
      - sysv-rc-conf
      - python-pip
      - python-dev
      - libmysqlclient-dev

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers

      gather_facts: no
      become: true

      vars:
        aptget_update_cache_valid_time: 1800
        aptget_distupgrade: true

      roles:
         - { role: CarlosLongarela.apt }

License
-------

GPLv2

Author Information
------------------

This role was created in 2017, May by [Carlos Longarela](mailto:carlos@longarela.eu), from [Taberna WordPress](https://tabernawp.com/).
