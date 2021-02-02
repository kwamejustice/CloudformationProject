# CloudformationProject

- This project is to deploy an application along with the necessary software into its matching infrastructure in an *AWS console*.

## The files _create.sh and update.sh_ are used to create the infrastructure and update infrasturcture with the changes made.

Content of the create.sh file

          ##!/bin/bash
           aws cloudformation create-stack \
           --stack-name $1 \
           --template-body file://$2 \
           --parameters file://$3 \
           --region=us-west-2

## Project content
  
 - created a Launch Configuration application to deploy four servers, two located in each of your private subnets.
 - The launch configuration are used by an auto-scaling group.
 - Two vCPUs and 4GB of RAM for the VMs,the Operating System used is Ubuntu 18. 
 - created an IAM Role that allows instances to use the S3 Service.
 - Servers inbound port is open for the Load Balancer and the Load Balancer Health Check traffic.
 - As for outbound, the servers has unrestricted internet access to be able to download and update its software.
 - The load balancer allows all public traffic (0.0.0.0/0) on port 80 inbound, which is the default HTTP port. 
 - Outbound, load balancer uses port 80 to reach the internal servers.
 - The application is deployed into private subnets with a Load Balancer located in a public subnet.
 
 ## The diagram in this repo explains the infrastructures architecture
