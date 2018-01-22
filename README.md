# UCLALib Ansible Role: Java

Installs Oracle Java on server. RPM is obtained directly from Oracle.

## Requirements

Only supports RHEL-family servers.

## Variables

`oracle_java_url` - defines the download URL for the Oracle Java rpm - No default is set - must specify in the play

`java_rpm_filename` - defines the filename of the Oracle Java rpm - file name is created based on the download URL

`oracle_java_version` - defines the version of Oracle to be installed - No default is set - must specify in the play - Expected use: `"java version \"1.8.0_161\""`

`java_rpm_md5` - defines the MD5 checksum of the Oracle Java rpm file - No default is set - must specify in play

`java_home` - defines the filesystem path to the installed JRE - Default set to: `/usr/java/latest/jre`

## Example Playbook:
```
---
- name: uclalib_java_app.yml
  sudo: true
  hosts: test
  vars:
    oracle_java_url: http://download.oracle.com/otn-pub/java/jdk/8u161-b12/2f38c3b165be4555a1fa6e98c45e0808/jdk-8u161-linux-x64.rpm
    oracle_java_version: "java version \"1.8.0_161\""
    java_rpm_md5: f396f618b7c059089240563d2c46b5fc

  roles:
    - { role: uclalib_role_java }
    - { role: uclalib_role_java_app }

```
