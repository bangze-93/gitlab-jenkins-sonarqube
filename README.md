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
### Open your favorite browser and access
#### GitLab
http://192.168.200.41

![image](https://github.com/bangze-93/gitlab-jenkins-sonarqube/assets/52735927/6df860c4-3957-477c-865a-47d43a820f14)
#### Jenkins
http://192.168.200.42:8080

![image](https://github.com/bangze-93/gitlab-jenkins-sonarqube/assets/52735927/d7087022-2b70-497a-9918-455dee8d208c)
#### SonarQube
http://192.168.200.43:9000

![image](https://github.com/bangze-93/gitlab-jenkins-sonarqube/assets/52735927/c1ea6cf4-a844-4b63-9f86-a84c3d253e77)

