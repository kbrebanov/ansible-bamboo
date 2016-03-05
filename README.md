bamboo
======

[![Build Status](https://travis-ci.org/kbrebanov/ansible-bamboo.svg?branch=master)](https://travis-ci.org/kbrebanov/ansible-bamboo)

Installs Bamboo

Requirements
------------

This role requires Ansible 1.9 or higher.

Role Variables
--------------

| Name                      | Default                                                          | Description                  |
|---------------------------|------------------------------------------------------------------|------------------------------|
| bamboo_version            | 5.10.2                                                           | Version of Bamboo to install |
| bamboo_archive_sha256sum  | 9d7b3853a2d91f529f8153a2fd57da903e9c1a2bfd91d304428b6598c9af5937 | SHA 256 checksum of archive  |
| bamboo_jvm_minimum_memory | 256m                                                             | Bamboo JVM minimum memory    |
| bamboo_jvm_maximum_memory | 384m                                                             | Bamboo JVM maximum memory    |
| bamboo_jvm_stack_size     | 512k                                                             | Bamboo JVM stack size        |

Dependencies
------------

- kbrebanov.java (Java 8)

Example Playbook
----------------

Install Bamboo
```
- hosts: all
  roles:
    - { role: kbrebanov.bamboo }
```

Install Bamboo specifying version
```
- hosts: all
  roles:
    - { role: kbrebanov.bamboo, bamboo_version: 5.8.0 bamboo_archive_sha256sum: 88e2463a775fe6078c6ccf5142117384beb0be4d73815ce2146e0f05cde771f5 }
```

Install Bamboo specifying Bamboo JVM memory
```
- hosts: all
  roles:
    - { role: kbrebanov.bamboo, bamboo_jvm_minimum_memory: 3000m, bamboo_jvm_maximum_memory: 4096m }
```

License
-------

BSD

Author Information
------------------

Kevin Brebanov
