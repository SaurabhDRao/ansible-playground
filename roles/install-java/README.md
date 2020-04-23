Install Java
=========

This role installs the default Java JDK and JRE on Debian family.

Role Variables
--------------

Currently this role installs the latest verison. Might add some variables so that users can install any specific version

Example Playbook
----------------

    - hosts: servers
      roles:
         - install-java
