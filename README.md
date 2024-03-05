# FleetCart Cloud Project

## Overview

<!-- Goal: host website on cloud -->
In this project, I implemented a highly available 3 tier architecture on AWS to host an ecommerce website titled `FleetCart`. This cloud solution consists of core AWS resources, including compute, load balancing, and database services to provide a scalable and resilient architecture.

<!-- What are my architecture styles? -->
## Ecommerce Website Architecture
In 3 tier architecture, applications are organized into three logical tiers: presentation layer, the business logic layer and the data storage layer. The ecommerce web applicatuin follows the client-server paradigm and consists of a frontend, backend and database. 

<!-- What are my key services? -->
## AWS Key Services
The key AWS services used to built this highly available, scalable and fault tolerant cloud solution are VPC, EC2, S3,RDS, Amazon Route 53, Application Load Balancer, Auto Scaling, NAT Gateways, Internet Gateways and IAM.


<!-- Insert diagram of architecture -->
## Cloud Solution Architecture

![architecture image](/assets/cloud-project-ecommerce.png)

For this AWS cloud solution, I created the following architecutre:
1. VPC with public and private subnets
2. Internet gateway to allow communication between our instances in the VPC and internet. NAT Gatways to allow instances in the private subnets to access the internet (but external services cannot initiate connection with those instances).
3. 2 Availabilty zones for high Availabilty and fault tolerance.
4. Private subnets for the webserver and database to protect them from unauthorized access.
5. MySQL relational database to storage, manange and track real-time business information.
6. EC2 instances to host the website.
7. Application Load Balancer to distribute web traffic across autoscaling group of EC2 instances in multiple Availabilty zones.
8. Auto Scaling Group to dynamically create EC2 instances to make website highly available, scalable, elastic and fault-tolerance
9. Route 53 to register domain name and create highly avaialable and scalalbe domain name system (DNS) to route end useres to web application.
10. AWS to store web assets for site
11. IAM role with S3 policy to allow EC2 instance to access and download webfiles from S3 bucket.
12. Once the website is successfully installed on EC2 instance, I created an AMI for the customized EC2 instance to easily launch future EC2 instances of the website.