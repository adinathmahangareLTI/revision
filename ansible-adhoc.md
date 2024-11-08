### diff between ansible and puppet
- agentless
- simple to write: yaml
- add custom modules: python
- can be run in windows and linux
  

### steps
- create ansible-server and ansible-host EC2 instances
- install ansible on ansible-server
- add ansible.cfg in /etc/ansible
- add /etc/ansible/hosts
- create ansible playbooks
- run ansible playbooks using "ansible-playbook playbook-name"
- run ansible adhoc commands for simple single commands to be run in all hosts or check status of some process in hosts
- to run adhoc commands <b>ansible all -m "shell" -a "touch devopsclass"</b>
- <b>ansible all -m "shell" -a "df"</b>


### installinng and starting nginx server on host

```bash
---
- name: Install and start nginx
  hosts: all

  tasks:
    - name: install nginx
      yum:
        name: nginx
        state: present

    - name: start nginx
      service:
        name: nginx
        state: started
```
