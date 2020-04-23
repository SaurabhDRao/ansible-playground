Install Kubernetes
=========

This role installs a specific version of Kubernetes. Before installing kuberentes packages, it first install docker.

Role Variables
--------------

Currently this role installs a hardcoded specific version. Might add some variables so that users can install any specific version

Example Playbook
----------------

    - hosts: servers
      roles:
         - install-kubernetes
