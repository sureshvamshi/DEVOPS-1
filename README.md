# ANSIBLE
---
## Ansible Workflow

<img src="Ansible_Workflow1.PNG"/>

---
## Ansible Introduction

<img src="Ansible_Introduction.PNG"/>

---
## Ansible Features

<img src="Ansible_Features.PNG"/>

---
## Ansible Installation and setup
```
	1. Create 3 machines in AWS
		a. One machine as Ansible-Controller ( requirements: 2 CPU's and 2 GB RAM)
		b. Two machines as targets (target1 and target2)
	2. Connect to Ansible Linux EC2 Terminal through mobaxterm or putty.
	3. Switch to root user.
	4. Update Server Packages.
	yum update -y
	5. Change the hostname (computer name) of Ansible-Controller as ansible-controller and target machines as target1 and target2 using the following command
	
	hostnamectl set-hostname 'ansible-controller'
	hostnamectl set-hostname 'target1'
	hostnamectl set-hostname 'target2'
	
	reboot all the 3 servers  - sudo reboot
	
	6. Install the ansible.
		○ install Ansible pre-requisites.
		Download epel repository.
			wget https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
		○ Install epel repository.
		yum install epel-release-latest-7.noarch.rpm -y
		○ Update epel repository.
		yum update -y
		○ Install all individual packages inside the repository
		yum install git python python-devel python-pip openssl ansible -y
		○ ansible --version

	7. add the following line under [default] section in /etc/ansible/ansible.cfg
	interpreter_python=auto_silent

	8. SSH connection to targets
		○ SSH connection to targets must be working 
		○ one time setup need to do on target machines and controller
		○ Create ssh key on controller machine and copy that key to target machines authorized_keys file.
			§ Ssh-keygen (ansible-controller)
			§ Copy /home/ec2-user/.ssh/id_rsa.pub file content to 2 target machines inside /home/ec2-user/.ssh/authorized_keys file.
	9. Go to the file /etc/ansible/hosts and add target machines IP Addresses inside the file. Look at the following
		[webservers]
		IP1
		IP2

	10. Do a ping test
	ansible all -m ping
```
---
## ansible commands
```
  331  cd test/
  332  ls
  333  vi inventory.txt
  334  ansible --version
  335  clear
  336  ansible all -m ping
  337  ansible all -m ping -i inventory.txt
  338  ansible target1 -m ping -i inventory.txt
  339  ansible target2 -m ping -i inventory.txt
  340  ansible webservers -m ping -i inventory.txt
  341  clear
  342  cat inventory.txt
  343  ansible all -m ping -i inventory.txt
  344*
  345  ansible all -m ping -i inventory.txt
  346  clear
  347  ls
  348  cat playbook.yml
  349  clear
  350  cat playbook.yml
  351  clear
  352  cat inventory.txt
  353  clear
  354  ls
  355  ansible-playbook playbook.yml -i inventory.txt
```
---
## ansible-playbook commands
```
 358  cat playbook-packageinstall.yml
  359  cp playbook-packageinstall.yml playbook-packageinstall2.yml
  360  clear
  361  ls
  362  vi playbook-packageinstall2.yml
  363  mv  playbook-packageinstall2 playbook-httpdinstall.yml
  364  mv  playbook-packageinstall2.yml playbook-httpdinstall.yml
  365  clear
  366  ls
  367  ansible-playbook playbook-httpdinstall.yml -i inventory.txt
  368  cat playbook-httpdinstall.yml
  369  clear
  370  vi playbook-httpdinstall.yml
  371  ansible-playbook playbook-httpdinstall.yml -i inventory.txt
  372  clear
  373  vi playbook-httpdinstall.yml
  374  ansible-playbook playbook-httpdinstall.yml -i inventory.txt
  375  clear
  376  vi playbook-httpdinstall.yml
  377  ansible-playbook playbook-httpdinstall.yml -i inventory.txt
  378  vi playbook-httpdinstall.yml
  379  clear
  380  ansible-playbook playbook-httpdinstall.yml -i inventory.txt
  381  clear
  382  cat playbook.yml
  383  cat playbook-httpdinstall.yml
  384  clear
  385  ansible --version
  386  cat playbook.yml
  387  clear
  388  cat playbook.yml
  389  clear
  390  cat playbook-httpdinstall.yml
  391  vi playbook-httpdinstall.yml
  392  clear
  393  ansible-playbook playbook-httpdinstall.yml -i inventory.txt
  394  clear
  395  cat playbook-httpdinstall.yml
  396  clear
  397  cat playbook-httpdinstall.yml
  398  clear
  399  vi playbook-httpdinstall.yml
  400  ansible-playbook playbook-httpdinstall.yml -i inventory.txt
  401  clear
  402  vi playbook-httpdinstall.yml
  403  cat playbook-httpdinstall.yml
  404  clear
  405  ansible-playbook playbook-httpdinstall.yml -i inventory.txt
  406  clear
  407  ls
  408  cat inventory.txt
  409  celar
  410  clear
  411  vi inventory.txt
  412  clear
  413  vi playbook-httpdinstall.yml
  414  ansible-playbook playbook-httpdinstall.yml -i inventory.txt
  415  cat inventory.txt
```
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
## Ansible Variables
1. The playbook is used to update name server entry into resolv.conf file on localhost. The name server information is also updated in the inventory file as a variable nameserver_ip. Refer to the inventory file.


Replace the ip of the name server in this playbook to use the value from the inventory file, so that in the future if you had to make any changes you simply have to update the inventory file.
```
-
    name: 'Update nameserver entry into resolv.conf file on localhost'
    hosts: localhost
    tasks:
        -
            name: 'Update nameserver entry into resolv.conf file'
            lineinfile:
                path: /etc/resolv.conf
                line: 'nameserver {{  nameserver_ip  }}'
```
2. We have added a new task to disable SNMP port in the playbook. However the port is hardcoded in the playbook. Update the inventory file to add a new variable snmp_port and assign the value used here. Then update the playbook to use value from the variable.


Remember to use curly braces around the variable name.
```
-
    name: 'Update nameserver entry into resolv.conf file on localhost'
    hosts: localhost
    tasks:
        -
            name: 'Update nameserver entry into resolv.conf file'
            lineinfile:
                path: /etc/resolv.conf
                line: 'nameserver {{ nameserver_ip }}'
        -
            name: 'Disable SNMP Port'
            firewalld:
                port: '{{ snmp_port }}'
                permanent: true
                state: disabled
```
3. We are printing some personal information to the screen. We would like to move the car_model, country_name and title to a variable defined at the play level.


Create three new variables (car_model, country_name and title) under the play and move the values over. Use the variables in the task.
```
-
    hosts: localhost
    vars:
        car_model: 'BMW M3'
        country_name: USA
        title: 'Systems Engineer'
    tasks:
        -
            command: 'echo "My car''s model is {{ car_model }}"'
        -
            command: 'echo "I live in the {{ country_name }}"'
        -
            command: 'echo "I work as a {{ title }}"'
```
Inventory file
```
localhost ansible_connection=localhost nameserver_ip=10.1.250.10 snmp_port=160-161
```
---
