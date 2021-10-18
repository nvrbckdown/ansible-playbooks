# Server initial configuration with Ansible
 
## Feel the power of ANSIBLE PLAYBOOK!
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
user: user_name
password: user_password
ssh_key_filename: ssh_key_file_name
pemfile_path: pem_file_path # path where you want to save pem file on your local machine!
```
---
Third. Run ansible command
```bash
# -i host.yaml means use this file as inventory file

ansible-playbook -i hosts.yaml playbook.yaml
```
