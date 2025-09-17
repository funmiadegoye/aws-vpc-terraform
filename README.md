aws-vpc-terraform

Automated AWS VPC provisioning using Terraform with public/private subnets, NAT Gateway, Internet Gateway, and EC2 instances. Demonstrates Infrastructure as Code and cloud networking best practices.

Project Overview

This project provisions a secure and scalable AWS Virtual Private Cloud (VPC) environment using Terraform. It includes:

Public and private subnets

NAT Gateway

Internet Gateway

Route tables

Security groups

An EC2 instance

The setup follows AWS best practices for networking, security, and high availability.

Key Features:

Fully automated infrastructure provisioning with Terraform

Two public and two private subnets across different availability zones

Internet Gateway for public subnet connectivity

NAT Gateway for private subnet outbound traffic

Custom route tables for subnet traffic routing

Security groups with controlled inbound/outbound rules

EC2 instance deployed in a public subnet

Ready-to-use for future CI/CD, Docker, and Kubernetes deployments

Project Structure
aws-vpc-terraform/
├── main.tf             # Core infrastructure resources
├── variables.tf        # Input variables for customization
├── outputs.tf          # Output values (e.g., VPC ID, subnet IDs)
├── terraform.tfvars    # User-specific variable values
├── provider.tf         # AWS provider configuration
├── README.md           # Project documentation

Prerequisites

Terraform >= 1.5.0

AWS CLI configured with IAM user credentials

Basic knowledge of AWS networking (VPC, subnets, security groups)

AWS account with sufficient permissions

Getting Started

Clone the repository

git clone https://github.com/yourusername/aws-vpc-terraform.git
cd aws-vpc-terraform


Configure Terraform variables
Update terraform.tfvars with your preferred values:

region = "us-east-1"
vpc_cidr = "10.0.0.0/16"
public_subnet_cidrs = ["10.0.1.0/24", "10.0.2.0/24"]
private_subnet_cidrs = ["10.0.101.0/24", "10.0.102.0/24"]


Initialize Terraform

terraform init


Review the plan

terraform plan


Apply the infrastructure

terraform apply


Destroy resources (optional)

terraform destroy

Architecture Diagram

Description:

Public subnets: Hosts resources accessible from the internet (e.g., EC2 with public IP)

Private subnets: Internal resources (e.g., databases) with no direct internet access

NAT Gateway: Allows outbound internet access for private subnet instances

Route Tables: Ensure correct traffic flow between subnets, IGW, and NAT

You can add a diagram image here once created:

![VPC Architecture](link-to-diagram.png)

Skills Demonstrated

Infrastructure as Code (Terraform)

AWS Networking (VPC, subnets, NAT/IGW, route tables)

Security best practices (security groups)

Automated resource provisioning

Next Steps / Enhancements

Deploy a multi-tier web application using the VPC

Integrate a CI/CD pipeline for automated deployments

Add monitoring and logging with CloudWatch

Use Terraform modules for reusable infrastructure






