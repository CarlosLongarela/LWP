Ansible Role: PhpMyAdmin
=========

[![Build Status](https://travis-ci.org/CarlosLongarela/ansible-role-phpmyadmin.svg?branch=master)](https://travis-ci.org/CarlosLongarela/ansible-role-phpmyadmin)
[![Percentage of issues still open](http://isitmaintained.com/badge/open/CarlosLongarela/ansible-role-phpmyadmin.svg)](http://isitmaintained.com/project/CarlosLongarela/ansible-role-phpmyadmin "Percentage of issues still open")
[![Average time to resolve an issue](http://isitmaintained.com/badge/resolution/CarlosLongarela/ansible-role-phpmyadmin.svg)](http://isitmaintained.com/project/CarlosLongarela/ansible-role-phpmyadmin "Average time to resolve an issue")

Install PhpMyAdmin with config file and blowfish hash.

Requirements
------------

None.

Role Variables
--------------

    phpmyadmin_folder: "/home/webs/phpmyadmin"


Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers

      gather_facts: no
      become: true

      vars:
        phpmyadmin_folder: "/home/webs/prestashop.test/public/phpmyadmin"

       roles:
         - { role: CarlosLongarela.phpmyadmin }

License
-------

GPLv2

Author Information
------------------

This role was created in 2017, May by [Carlos Longarela](mailto:carlos@longarela.eu), from [Taberna WordPress](https://tabernawp.com/).
