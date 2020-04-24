# Ansible Playground

This repository includes various ansible roles for installing some packages.

### Prerequisites

* A set of remote machines that can be reached through passwordless ssh from the control machine.
* IP addresses of all those remote machines.
* A user with sudo privilages on those remote machines.

### How to Execute

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

### Known Issues

1. Sometimes an error occurs when updating the apt cache. Just comment out the below line in the appropriate task files.
```
update_cache: true
```

2. If you get error saying `/usr/bin/python3 does not exist`, then remove the below lines from the inventory file.
```
[all:vars]
ansible_python_interpreter=/usr/bin/python3
```
