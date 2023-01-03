Instructions for deployment of the project's backend,frontend and the mysql server, depending on each scenario:



- Ansible Deploy Scenario:

Run mainPlaybook.yaml playbook at ansible-deploy/playbooks/mainPlaybook.yaml with desired host as an extra variable. This will install and deploy the React-Frontned part on an NginX proxy server, Spring-Backend on an Apache Tomcat server to connect with the MySQL database server.

Command:
ansible-playbook ansible-deploy/playbooks/mainPlaybook.yaml -i hosts -e "targetMachine= 'YOUR_HOST_IP'"

- Docker Deploy Scenario:


Run mainPlaybook.yaml playbook at docker-deploy/playbooks/mainPlaybook.yaml with desired host as an extra variable. This will install and deploy the project as 3 independent docker containers.

Command:
ansible-playbook docker-deploy/playbooks/mainPlaybook.yaml -i hosts -e "targetMachine= 'YOUR_HOST_IP'"


