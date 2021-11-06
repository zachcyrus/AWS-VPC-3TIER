# AWS-VPC-3TIER Documentation

## Purpose:

The purpose of this project is to create a classic 3 tier architecture within our own virtual private cloud(VPC) hosted by AWS. 

This 3 tier architecture will consist of an nginx reverse proxy which will retrieve traffic, this proxy will then redirect traffic to our server application hosting Phpmyadmin, which will then communicate with MySQL database hosted by AWS. 

## Steps to replicate:

### Creating a VPC in AWS

1. Create a new VPC through the AWS console with the following configurations:
- Name: Kura-3-Tier
- CIDR Block: 10.0.0.0/16 (This will provide you with a range of ip address your VPC can use)
- IpV6 Block: None
- Tenency: Default


### Creating Private and Public Subnets

1. First up we are going to create a public subnets which will host our Nginx reverse proxy. This is set up in our public subnet to allow for clients to actually connect to it. 

2. Navigate to the subnets tab in the VPC section of AWS and lick create subnets.

3. Choose the VPC you recently just created, and configure the 4 following subnets. 