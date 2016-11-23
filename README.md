postfix
=========

This roles installs and configures postfix

[![Build Status](https://travis-ci.org/Rheinwerk/ansible-role-postfix.svg?branch=master)](https://travis-ci.org/Rheinwerk/ansible-role-postfix)

Requirements
------------

None.

Role Variables
--------------

There is one variable that drive this role: `_postfix`. `_postfix` is a map that contains all configuration and settings for this role. Please see `defaults/main.yml` for details.

Dependencies
------------

None.

Example Playbook
----------------

The general contract of this role is to take the variables map `_postfix` from `defaults/main.yml` as a template for your configuration and pass that configuration as a parameter to this role.

Example:
```
    - hosts: <HOST THAT IS ALLOWED TO MANAGE MYSQL>
      var:
        POSTFIX:
          mailname: host.domain
          myhostname: host.domain
          mynetworks:
            - 127.0.0.0/8
          inet_interfaces:
            - 127.0.0.1
          inet_protocols:
            - ipv4
          aliases:
            - { user: root, address: someone@example.com, state: present }
     roles:
        - { role: postfix, tags: [ 'postfix' ], _postfix: "{{ POSTFIX }}" }
```

License
-------

Please see LICENSE.

Author Information
------------------

Original author is [Lukas Pustina](https://github.com/lukaspustina) as member of the [Rheinwerk](https://github.com/Rheinwerk) project.

