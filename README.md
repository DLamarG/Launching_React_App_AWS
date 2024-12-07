### Launching_React_App_AWS

Step-by-Step Guide

## 1. Create a VPC:
* Log in to the AWS Management Console.
* Navigate to the VPC service.
* Click "Create VPC."
* Choose a CIDR block (e.g., 10.0.0.0/16).
* Click "Create VPC."


## 2. Create a Public Subnet:
In the VPC dashboard, select the newly created VPC.
Click "Subnets."
Click "Create subnet."
Choose an availability zone.
Specify a CIDR block (e.g., 10.0.0.0/24).
Select "Public subnet" and enable Auto-assign Public IP.
Click "Create subnet."


## 3. Create an Internet Gateway:
In the VPC dashboard, select the newly created VPC.
Click "Internet Gateways."
Click "Create Internet Gateway."
Name the Internet Gateway.
Click "Create Internet Gateway."


## 4. Attach the Internet Gateway to the VPC:
In the VPC dashboard, select the newly created VPC.
Click "Internet Gateways."
Select the Internet Gateway you created.
Click "Attach to VPC."
Choose the VPC you created.
Click "Attach Internet Gateway."


## 5. Create a Route Table:
In the VPC dashboard, select the newly created VPC.
Click "Route Tables."
Click "Create route table."
Name the route table.
Click "Create route table."


## 6. Create a Route for Internet Access:
In the VPC dashboard, select the newly created route table.
Click "Routes."
Click "Add route."
Set the Destination CIDR block to 0.0.0.0/0.
Select the Internet Gateway as the target.
Click "Save."


## 7. Associate the Route Table with the Subnet:
In the VPC dashboard, select the newly created subnet.
Click the "Route Table associations" tab.
Click "Edit route tables."
Select the route table you created.
Click "Save."


## 8. Create a Security Group:
In the VPC dashboard, select the newly created VPC.
Click "Security Groups."
Click "Create security group."
Name the security group.
Add inbound rules:
Type: HTTP
Protocol: TCP
Port Range: 80
Source: 0.0.0.0/0
Type: HTTPS
Protocol: TCP
Port Range: 443
Source: 0.0.0.0/0
Type: SSH
Protocol: TCP
Port Range: 22
Source: 0.0.0.0/0
Type: Custom TCP
Protocol: TCP
Port Range: 3000
Source: 0.0.0.0/0
Click "Create security group."


## 9. Launch an EC2 Instance:
In the EC2 dashboard, click "Launch Instance."
Choose an Amazon Machine Image (AMI) (e.g., Amazon Linux 2).
Choose the instance type (e.g., t2.micro).
Configure the security group you created.
Choose the subnet you created.
Review and launch the instance.


## 10. Configure the EC2 Instance:
Connect to the instance using SSH.
Install Node.js and npm.
Clone your React app repository.
Install dependencies: npm install
Start the React app: npm start
