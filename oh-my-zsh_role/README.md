## Ansible Oh-My-Zsh Role installation
---
Go to default/main.yaml file and edit this 👇
this block assign *zsh* for your user and add plugins below to _.zshrc_ file

```bash
users:
  - username: ubuntu
    oh_my_zsh:
      theme: robbyrussell
      plugins:
        - git
        - zsh-completions
        - zsh-syntax-highlighting 
        - zsh-autosuggestions
```
---
You have to fill hosts.yaml file with your credentials!
```bash
web:
  hosts:
    server:
  vars:
    ansible_host: 191.192.193.194
    ansible_user: Sudoer
    ansible_ssh_private_key_file: ~/somewhere/*.pem # if you have
    ansible_password: 123321 # if you use pem key comment password! 
```
---
Open vars.yaml! Plugins should be as presented!\
***zsh-systex-highlighting*** you have to install manually!
```bash
plugins:
    - zsh-autosuggestions
    - zsh-completions
    - zsh-syntax-highlighting
```
---
Command to run all this magic:
```bash
ansible-playbook playbook.yaml
```