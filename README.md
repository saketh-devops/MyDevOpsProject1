# MyDevOpsProject1
####
This is a readme file for devops projects
#####

Steps followed to complete the project:

Pre-requites:
Created AWS-FREE tier account
Gathered the below details from AWS-EC2.
---
ACCESS_KEY,SECRET_KEY,AMI_ID,SUBNET_ID
---
Created a key-pair and downloaed on my laptop.
installed virtual box
created a virtual machine and installed ubuntu 64 bit on it.
installed ansible on it
created a details-aws.yml file to store the AWS deatils.
Created spinup-aws-instance.yml file.
----
This will read the details from details-aws.yml file and create an EC2 instance in AWS. 
It will create a file new-host and push all the ipddress and key name details there.
----
created configure.machine.yml file
--
this will instance apache tomcat
creates self signed ssl certs and installs them
creates ssl conf file for apace
creates redirect conf file and rewrite rules.
created index.html file to display hello world.
restart tomcat
--
created test-config.yml
---
Checks the 80,443 ports
check if the redrection is properly done or not
checks if ssl are installed and working or not.
-----

How to run:
----
Create AWS-FREE tier account
Gather the details "ACCESS_KEY,SECRET_KEY,AMI_ID,SUBNET_ID".
Create a key-pair and download it.
Installed ansible on your servers/vms.
create a directory and unzip devops-project.zip file.
run the commands one by one:
---
ansible-playbook spinup-aws-instance.yml
ansible-playbook configure.machine.yml -i new-host
ansible-playbook test-config.yml INSTANCE_IP=IPADDRESSFROMNEWHOSTFILE
----












