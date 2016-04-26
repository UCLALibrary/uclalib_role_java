# UCLALib Ansible Role: Java

Installs Java on RHEL linux servers from an official RedHat repository.

## Default Variables

  java_package - define the java package name to install
  java_reponame - define the java repository to enable in subscription-manager

This role first determines if it needs to enable the repository defined by `java_reponame`.

Then installs the package defined by `java_package`.

Example use in a playbook:
```
---
- name: uclalib_java_app.yml
  sudo: true
  hosts: test

  roles:
    - { role: uclalib_role_java }
    - { role: uclalib_role_java_app }

```
