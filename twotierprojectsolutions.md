#Two tier solution on DB - Project.


DB Project
Introduction
This project would be used to test VPC, EC2 and S3 skills





User Story:
A web application will need to be created which contains a database. We have decided to use AWS PaaS in the creation of this web application. There will be 2 private database servers, 1 public bastion server and 1 public web server.

For the Private Server:
i. db_server : this private server will be connected to the internet in order to update the latest packages

ii. db2_server : this private server will not be connected to the internet but will be connected to the S3 AWS service only


For the Public Server:
i. bastion_server : should be able to connect the internet and have access to the db_server and db2_server

ii. _web_server _: should have apache installed





Naming Convention
VPC:
We need to create a VPC containing 1 private and 1 public subnet

a. Name of public subnet : jjtech_public_subnet

  i.AZ: us-west-2a
  ii. CIDR : 10.0.1.0/24
  
b. Name of private subnet : jjtech_private_subnet

  i.AZ: us-west-2b
  ii. CIDR : 10.0.2.0/24
  
c. Name of VPC : JJTechVPC 
  i. region: us-west-2
  ii. CIDR : 10.0.0.0/16
Instances :
We need to create 4 instances :

a. Name of instance 1 : bastion_server

  i.subnet: public
  
b. Name of instance 2 : web_server

  i.subnet: public
  
c. Name of instance 3 : db_server

  i.subnet: private
  
d. Name of instance 4 : db2_server

  i.subnet: private




ASSIGNMENT :

Part 1
Create an architectural diagram highlighting the user-story and naming convention above.

TIPS:
This incorporates concepts such as :

Endpoints
NAT Gateways
Route Tables
Internet Gateway
Make sure to incoporate these into your architectural diagram. This diagram will be essential when setting things up in the AWS console. This





Part 2
Using the architecture above, recreate the architecture in the AWS console.


Reminders :

Follow the naming convention in the architectural diagram
Follow best security practices (hint: do you use an IAM policy or hard code you access and secret key into you ec2 instances)



Notes:
1) db_server : is connected to the internet, you will be downloading sql to this server. Use the website in the block below to install the sql server

https://tecadmin.net/how-to-install-mysql-8-on-amazon-linux-2/ 

**2) db_server2** : you will need to connect to an s3 bucket and prove it works.


#Architectural solution.



![DB-project](https://user-images.githubusercontent.com/120702469/233757440-4f28cfa2-fefe-4295-919a-b6e60f70f308.jpg)
