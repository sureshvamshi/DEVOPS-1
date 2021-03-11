# ANSIBLE
---
## Ansible Modules Examples
1. Update the playbook with a play to Execute a script on all web server nodes(web_nodes). The script is located at /tmp/install_script.sh
```
Answer:
- name: 'Execute a script on all web server nodes'
  hosts: web_nodes
  tasks:
  - name: 'Execute a script on all web server nodes'
    script: /tmp/install_script.sh
```
2. Update the playbook to add a new task to start httpd services on all web nodes

Use the Service module
```
Answer:
-
    name: 'Execute a script on all web server nodes'
    hosts: web_nodes
    tasks:
        -
            name: 'Execute a script'
            script: /tmp/install_script.sh
        -
            name: 'Start httpd service'
            service: 'name=httpd state=started'
```
3. Update the playbook to add a new task in the beginning to add an entry into /etc/resolv.conf file for hosts. The line to be added is nameserver 10.1.250.10


Note: The new task must be executed first, so place it accordingly.

Use the Lineinfile module
```
Answer:
-
    name: 'Execute a script on all web server nodes and start httpd service'
    hosts: web_nodes
    tasks:
        -
            name: 'Update entry into /etc/resolv.conf'
            lineinfile:
                path: /etc/resolv.conf
                line: 'nameserver 10.1.250.10'
        -
            name: 'Execute a script'
            script: /tmp/install_script.sh
        -
            name: 'Start httpd service'
            service:
                name: httpd
                state: present

```
4. Update the playbook to add a new task at second position (right after adding entry to resolv.conf) to create a new web user.


Use the user module for this. User details to be used are given below:
Username: web_user
uid: 1040
group: developers
```
Answer:
-
    name: 'Execute a script on all web server nodes and start httpd service'
    hosts: web_nodes
    tasks:
        -
            name: 'Update entry into /etc/resolv.conf'
            lineinfile:
                path: /etc/resolv.conf
                line: 'nameserver 10.1.250.10'
        -
            name: 'Create a new user'
            user:
                name: web_user
                uid: 1040
                group: developers
        -
            name: 'Execute a script'
            script: /tmp/install_script.sh
        -
            name: 'Start httpd service'
            service:
                name: httpd
                state: present
```
---

