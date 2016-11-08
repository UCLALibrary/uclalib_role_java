# UCLALib Ansible Role: Java

Installs Java on a server in the RHEL family, optionally from an official RedHat repository.

## Default Variables

  java_package - define the java package name to install (defaults to Oracle JDK 8)
  java_reponame - define the java repository to enable in subscription-manager

This role first determines if it needs to enable the repository defined by `java_reponame`
(only for RHEL, not for any other distribution)

Then installs the package defined by `java_package`.

Example use in a playbook:
```
---
- name: uclalib_java_app.yml
  sudo: true
  hosts: test

  # Optionally specify the java_package to use, if not specified will default to Oracle JDK 8
    - java_package: java-1.7.0-openjdk-devel.x86_64

  roles:
    - { role: uclalib_role_java }
    - { role: uclalib_role_java_app }

```
