# Server initial configuration with Ansible

## Setup list
- sudo user
- ssh-key
- nginx
- htop
- net-tools
- docker
- docker-compose

## Works on Ubuntu and CentOS

---
First. Write server cridentials to hosts.yaml

```bash
### You have to feel only ansible_host, user and password!
web:
  hosts:
    server:
  vars:
    ansible_host: IP_ADDRESS 
    ansible_user: root 
    ansible_password: PASSWORD
```
---
Second. Open vars dir and feel all fields of values.yaml

```bash
nginx: 'nginx' # by default latest, for version use nginx=1.18*
user: 'user_name'
password: 'user_password'
ssh_key_filename: 'ssh_key_file_name'
pemfile_path: 'pem_file_path' # path where you want to save pem file on your local machine!

# This vars will be only used if you need to create db and user
db_user: 'db_user_name'
db_password: 'db_user_password'
db_name: 'db_name'
```
---
Conditional check allows to use or skip any service. 
By default it is false if you need to install any change value to true
```bash
user_check: false
ssh_key_check: false
nginx_check: false
es_commands_check: false
docker_check: false
postgresql_check: false
```
---
Third. Run ansible command
```bash
# -i host.yaml means use this file as inventory file

ansible-playbook -i hosts.yaml playbook.yaml
```
---
