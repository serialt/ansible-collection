# Ansible Collection - serialt.ansible

Documentation for the collection.

## Download Ansible Colletion

```shell
ansible-galaxy collection install git@github.com:serialt/ansible-collection.git

```

**Use requirements.yml**
```shell
# requirements.yml
collections:
- name: git@github.com:serialt/ansible-collection.git
  git: git 
  version: master


$ [serialt@imau sugar]$ ansible-galaxy collection install -r requirements.yml
```


## Use Collection
```yaml
# example 1:
- hosts: serialt
  become: yes
  become_user: root
  vars:
    go_version: "1.20.1"
  tasks:
  roles:
    - serialt.ansible.go

# example 2:
- hosts: serialt
  become: yes
  become_user: root
  tasks:
  roles:
    - role: serialt.ansible.go
      go_version: "1.19.5"
 
# example 3:
- hosts: serialt
  become: yes
  become_user: root
  vars:
    go_version: "1.20.2"
  tasks:
    - import_role:
        name: serialt.ansible.go
        
# example 4:
- hosts: localhost
  connection: local
  tasks:
    - name: Include role
      include_role:
        name: serialt.ansible.<role_name>
      vars:
        var1: value1
        var2: value2 
```