# Automation-of-RDS-Using-Ansible
**Project Overview**
This project demonstrates the automation of Amazon RDS instance creation using Ansible on a CentOS 7 EC2 instance.

**Prerequisites**
1. AWS Account
2. EC2 Instance (CentOS 7)
3. IAM Role with AmazonRDSFullAccess policy
4. Ansible installed (Which can be done in the instance iself)
5. Python pip and boto library installed

**Setup & Execution**
1. Launch EC2 Instance
Start a CentOS 7 instance in AWS.

2. Install Ansible & Dependencies in the EC2 instance created
sudo yum update -y && 
sudo yum install epel-release -y && 
sudo yum install ansible -y && 
sudo yum install python-pip -y && 
pip install boto

3. Configure IAM Role
AWS Console -> IAM -> Roles -> Create Role (AmazonRDSFullAccess)
Select EC2 -> Attach AmazonRDSFullAccess policy
Name the role and create it.
Attach the role to the EC2 instance:
Go to EC2 -> Actions -> Security -> Modify IAM Role -> Select the created role

4. Create the Ansible Playbook
Create a file named playbook.yml by using command vi and add the content from the playbook file, The file is attached in the repository.

5. Execute the Playbook using below command
ansible-playbook playbook.yml

6. Verify RDS Instance 
Go to the RDS Console in AWS and confirm the instance is created. Connect to the instance via MySQL Workbench using the endpoint, username, and password which we specified in the playbook.

**Troubleshooting**
Ensure IAM permissions are correct.
Verify boto library is installed.
Check AWS Console logs if playbook fails.

**Expected Output**
Successful RDS instance creation visible on AWS Console.
Accessible MySQL database using Workbench.


