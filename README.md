Assignment 3:

We have four main files in this project. provider.tf contains the provider and region details, variables.tf contains variable types and default values, main.tf lists the resources to be created, and variables.tfvars is a file passed in the command prompt to take input values like CIDR blocks and regions.

To run the Terraform configuration files, we use three commands: terraform init to initialize the backend processes, terraform apply to create resources (with a confirmation prompt), and terraform destroy to delete created resources.

In this specific project, we created a VPC with three public and three private subnets in different availability zones in the same region, a public route table, a private route table, and an internet gateway. We also added .tfvars, .terraform.lock.hcl, and terraform.state to .gitignore.

Assignment 4:

In this project, we're setting up networking infrastructure using Terraform on AWS. We've installed the AWS CLI and Terraform, and created two users in the Dev and Demo AWS accounts with administrator access: "aws_cli_dev" and "aws_cli_demo". We create access keys under their security credentials and configure them in the AWS CLI for each profile.

To set up the virtual private cloud (VPC) network infrastructure in the AWS region according to inputs provided, we use three commands: terraform init to initialize the backend and provider plugins, terraform fmt to format the Terraform files in the directory, and terraform apply -var-file var.tfvars to create the VPC with subnets and an internet gateway, using configuration values in main.tf. The data.tf file contains the availability zones data source, and -var-file var.tfvars executes the application with the values defined in var.tfvars.

We also create an EC2 instance in the VPC and attach it to the configured GitHub secrets, and we use terraform destroy -var-file var.tfvars to destroy the network infrastructure.

Assignment 9:

This project involves uploading a Namecheap SSL certificate to AWS using the AWS CLI. We use the command aws --profile demo acm import-certificate --certificate fileb://Certificate.pem --certificate-chain fileb://CertificateChain.pem --private-key fileb://PrivateKey.pem, replacing the file paths with our own file paths and extensions.

We also add two separate KMS keys, one for encrypting EBS volumes and the other for encrypting RDS instances. Finally, we modify the load balancer security group ingress rule to run on port 443 (HTTPS) for secure web traffic.




