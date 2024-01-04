<!-- This file was automatically generated by the `geine`. Make all changes to `README.yaml` and run `make readme` to rebuild this file. -->


<p align="center"> <img src="https://user-images.githubusercontent.com/50652676/62451340-ba925480-b78b-11e9-99f0-13a8a9cc0afa.png" width="100" height="100"></p>

<h1 align="center">
    Ansible Role Docker Jenkins
</h1>

<p align="center" style="font-size: 1.2rem;">
    This ansible role is used to install Jenkins with docker on server.
     </p>


We eat, drink, sleep and most importantly love **DevOps**. DevOps always promotes automation and standardisation. While setting up various environments like local, dev, testing, production, etc. it is critical to maintain the same environment across. This can easily be achieved using automating the environment setup & installation with the help of ansible-playbooks.

Smaller roles are created for each environment elements; which also include tasks & tests. These roles can then be grouped together in [ansible-playbook](https://docs.ansible.com/ansible/latest/user_guide/playbooks_intro.html) to achieve the desired yet consistent results.




## Table of Contents
- [Example Playbook](#Example-Playbook)
- [Variables](#Variables)
- [License](#license)







## Example Playbook

**IMPORTANT:** Since the `master` branch used in `source` varies based on new modifications, we suggest that you use the release versions [here](https://github.com/cypik/ansible-role-docker-jenkins/releases).


```yaml
- hosts: localhost
  remote_user: root
  become: true
  roles:
    - cypik.ansible_role_docker_jenkins
```


## Variables

```yaml
  jenkins_version: "lts-alpine"
  jenkins_caddy_server_name: jenkins.cypik.com
  jenkins_opt_dir: "/opt/jenkins"
  jenkins_config_dir: "{{ jenkins_opt_dir }}/config"
  jenkins_tmp_dir: "{{ jenkins_opt_dir }}/tmp"
  jenkins_data_dir: "{{ jenkins_opt_dir }}/data"
  jenkins_https_port: "443"
  jenkins_http_port: "8080"
  jenkins_xmx: "{{ ( ansible_memtotal_mb * 0.20 ) | round(0, 'ceil') | int }}"
  jenkins_user: jenkins
  jenkins_group: jenkins
  jenkins_hostname: localhost
  jenkins_agent_port: "50001"
  jenkins_plugins:
    - git
    - ssh
  cert_path: "/root/config/star-cypik.crt"
  key_path: "/root/config/cypik-sub-domain-private-key.pem"

```

## License
This project is licensed under the MIT License - see the [LICENSE](https://github.com/cypik/ansible-role-jenkins/blob/master/LICENSE) file for details.


## Installation

```console
  $ ansible-galaxy install cypik.ansible_role_docker_jenkins
```






