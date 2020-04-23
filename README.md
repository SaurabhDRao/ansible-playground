# Ansible Playground

This repository includes various ansible roles for installing some packages.

### Prerequisites

* A set of remote machines that can be reached through ssh from the control machine.
* IP addresses of all those remote machines.
* A user with sudo privilages on those remote machines.

### How to execute

1. Open the inventory file in the directory and add in the IP addresses of the remote machines along with the username which has the sudo privilages.
```
192.168.0.3 ansible_user=myuser
ansi-poc-client.abc.com ansible_user=ansi
```

2. Open the main.yml in the root directory and add in the roles that you want to run.
```
roles:
- install-java
- install-nodejs
```

3. Run the below command in the project root directory
```
ansible-playbook -i inventory main.yml --ask-become-pass
```
