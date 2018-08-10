# UCLALib Ansible Role: Java

Ansible role to install Oracle Java on server. RPM is obtained directly from Oracle.

## Requirements

Only supports RHEL/CentOS-family servers.

For each version of Oracle Java you wish to download, ensure there is a corresponding vars file named:

`{{ oracle_java_version }}.yml` - for example: `1.8.0_161.yml`

This vars file should contain the variables: `oracle_java_url` and `java_rpm_md5` associated with the version of java you'd like to download/install.

## Variables

* `oracle_java_version` - defines the version of Oracle to be installed - no default is set - must specify in the play - Example: `1.8.0_161`. Also a corresponding vars file must exist with the appropriate `oracle_java_url` and `java_rpm_md5` entries.

* `oracle_java_url` - defines the url to obtain the version of java specified in `oracle_java_version`. This should be in included in the associated var file.

* `java_rpm_md5` - defines the md5 checksum to verify the downloaded rpm file. This should be in included in the associated var file.

## Example Playbook:
```
---
- name: uclalib_java_app.yml
  sudo: true
  hosts: test

  roles:
    - { role: uclalib_role_java, oracle_java_version: '1.8.0_161' }
    - { role: uclalib_role_java_app }
```
