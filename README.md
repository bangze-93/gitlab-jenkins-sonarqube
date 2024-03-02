# Install GitLab, Jenkins and SonarQube with Ansible on Ubuntu 20
### Adjust with your env
- #### <i> vars.yaml </i>
```
---
gitlab_version: 16.9.1-ce.0
jenkins_version: 2.440.1
sonarqube_version: lts-community
postgres_version: 12
gitlab_network: gitlab
jenkins_network: jenkins
sonarqube_network: sonarqube
postgres_user: sonar
postgres_password: Son4RQub3
...
```
- #### <i> hosts </i>
```
[nodes]
gitlab    ansible_host=192.168.200.41
jenkins   ansible_host=192.168.200.42
sonarqube ansible_host=192.168.200.43     

[all:vars]
ansible_connection=ssh
ansible_user=ubuntu
ansible_ssh_pass=ubuntu123
ansible_become_password=ubuntu123
```
### Run playbook
``` bash
ansible-playbook -i hosts playbook.yaml
``` 
