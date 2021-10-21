
[README.md](https://github.com/CDA1977/CDA1977/files/7388125/README.md)
The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/Project 1.jpg)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

     /etc/ansible/install-elk-playbook.yml
     
This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly _____, in addition to restricting _____ to the network.
- _TODO: Load balancers help to protect the the network by evenly distributing traffic to the various servies in the network. Because of this, load balancers offer an additional layer of security to networks because they help mitigate the impact of Dos attacks.
The use of a jumpbox provides for better security and monitering because its use provides a seperet security zone away from the rest of the network. In order to perform any administrative tast, Sys Admins must access the jump box to connect to other web servers on the network. Additionally, with this one-way-in/one-way-out approach, logging, monitoring, and mainternance only hase to be done on one host machine.there is only one otect? What is the advantage of a jump box?_

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system logs.
- Filebeat is used to detect changes in system data, and documents when those changes and create a log event of the change. 
-Metricbeat gathers statistical data from the of all the activity on the network and outputs that data to a file, location or program specified by the admin. system and 

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

|   Name  	|  Function  	|   IP Address  	| Operating System 	|
|:-------:	|:----------:	|:-------------:	|:----------------:	|
| JumpBox 	| Gateway    	| 52.188.147.35 	| Linux            	|
| Web-1   	| Server     	| 10.1.0.7      	| Linux            	|
| Web-2   	| Server     	| 10.1.0.8      	| Linux            	|
| Web-3   	| Server     	| 10.1.0.0/16   	| Linux            	|
| Elk-VM1 	| Elk Server 	| 10.0.0.4      	| Linux            	|


### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
My home network IP address

Machines within the network can only be accessed by _____.
52.188.147.35

A summary of the access policies in place can be found in the table below.

|   Name   	| Publicly Accessible 	|    Allowed IP Addresses    	|
|:--------:	|:-------------------:	|:--------------------------:	|
| Jump Box 	| Yes           	| SSH:My home network IPaddr 	|
| Web-1    	| No         	| 10.0.0.7     	|
| Web-2    	| No         	| 10.0.0.7     	|
| Web-3    	| No          	| 10.0.0.7     	|
| ELK-VM   	| No         	| 10.0.0.7     	|

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: It automates repeptitve & tedious tasks of configuring the ELK machine and standardizes the process.

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...
Install docker.io
Install Python-pip
Install docker container
Launch docker container: elk
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_
10.1.0.7
10.1.0.8
10.1.0.0/16

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_
Filebeat
Metricbeat

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._
Filebeats monitors system log files and file system changes.
Metricbeat monitors and collects system statistical data.
Both programs ford information on the ELK server for analysis/action item.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_ install elk.yml; /etc/ansible
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_  /etc/ansible/hosts  the ELK server (and the webservers)
- _Which URL do you navigate to in order to check that the ELK server is running? http://104.42.4.112:5601/app/kibana

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
