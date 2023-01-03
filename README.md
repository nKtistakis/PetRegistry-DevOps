# PetRegistry DevOps support

This repository contains all the necessary files for the _PetRegistry_ system to support DevOps practices.

## Installation Instructions

Instructions for deployment of the project's backend,frontend and the mysql server, depending on each scenario:


## Ansible Deploy Scenario:

Run mainPlaybook.yaml playbook at ansible-deploy/playbooks/mainPlaybook.yaml with desired host as an extra variable. This will install and deploy the React-Frontned part on an NginX proxy server, Spring-Backend on an Apache Tomcat server to connect with the MySQL database server.

Command:
- _ansible-playbook ansible-deploy/playbooks/mainPlaybook.yaml -i hosts -e "targetMachine= 'YOUR_HOST_IP'"_


## Docker Deploy Scenario:

Run mainPlaybook.yaml playbook at _docker-deploy/playbooks/mainPlaybook.yaml_ with desired host as an extra variable. This will install and deploy the project as 3 independent docker containers.

Command:
- _ansible-playbook docker-deploy/playbooks/mainPlaybook.yaml -i hosts -e "targetMachine= 'YOUR_HOST_IP'"_



#### Although the ansible playbooks can be ran mannualy, it recommended to set up a Jenkins server following the instructions:

### Jenkins Instructions

#### Step 1
- Set up a Jenkins server and add the appropriate keys

#### Step 2
- Create a job for each branch of the [PetRegistry-Frontend](https://github.com/nKtistakis/PetRegistry-Frontend) and [PetRegistry-Backend](https://github.com/nKtistakis/PetRegistry-Backend) repos.

### Step 3
- Link them to the branches by adding a GitHub hook to each job

### Step 4
- Order jenkins to run the appropriate playbooks everytime the job is triggered
