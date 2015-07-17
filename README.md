bamboo
======

[![Ansible Galaxy](https://img.shields.io/badge/galaxy-kbrebanov.bamboo-660198.svg)](https://galaxy.ansible.com/list#/roles/3383)

Installs Bamboo

Requirements
------------

This role requires Ansible 1.6 or higher.

Role Variables
--------------

| Name                      | Default                                                          | Description                  |
|---------------------------|------------------------------------------------------------------|------------------------------|
| bamboo_version            | 5.9.2                                                            | Version of Bamboo to install |
| bamboo_archive_sha256sum  | 9ad8acacbfc2de8a67d664adf123f0439ff7407d6bda10d51a4f6f81215b436e | SHA 256 checksum of archive  |
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
