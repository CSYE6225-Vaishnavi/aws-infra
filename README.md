# aws-infra

We have four main files for our Terraform configuration. 

1. The "provider.tf" file specifies the provider and region details. 
2. The "variables.tf" file defines all the variables, their types, and default values. 
3. The "main.tf" file lists all the resources that need to be created. 
4. The "variables.tfvars" file is used to pass values like CIDR blocks and regions via the command prompt.

To run the Terraform configuration, we need to use three commands. 
1. First, we use "terraform init" to prepare the backend processes for creation. 
2. Next, we use "terraform apply" to create all the resources listed in the configuration files, with a confirmation prompt before creation. 
3. Finally, we use "terraform destroy" to remove all the created resources.

In this configuration, we have created a VPC, three private subnets, and three public subnets in different availability zones within the same region. 
We have also created one public route table, one private route table, and one internet gateway. 
To keep our project organized, we have added ".tfvars", ".terraform.lock.hcl", and "terraform.state" to our gitignore file. Registering a Domain Name:

Go to Namecheap or any other domain registrar and register a domain name. If you're a student, you can get a free .me TLD domain from Namecheap with the Github Student Developer pack.

Configuring Amazon Route 53:

1. Log in to your AWS account and go to the Amazon Route 53 console.
2. Create a public hosted zone for your domain name by clicking on "Create Hosted Zone" and entering your domain name (e.g. yourdomainname.tld) in the "Domain Name" field. Leave the other fields as default and click on "Create Hosted Zone."
3. After creating the hosted zone, you will see four Route 53 name servers listed for your hosted zone. Copy these name servers to use in the next step.
4. Go to Namecheap or your domain registrar's console and update the domain's name servers to the Route 53 name servers you copied in the previous step.
5. Create a subdomain and hosted zone for the dev AWS account by clicking on "Create Hosted Zone" again and entering "dev" in the "Name" field and selecting "Public Hosted Zone" in the "Type" field. Enter your domain name (e.g. yourdomainname.tld) in the "Domain Name" field and leave the other fields as default. Click on "Create Hosted Zone."
6. After creating the dev hosted zone, you will see four Route 53 name servers listed for the hosted zone. Copy these name servers to use in the next step.
7. Go back to the hosted zone for your main domain name and click on "Create Record Set." Enter "dev" in the "Name" field, select "A - IPv4 address" in the "Type" field, and enter the IP address of your dev server in the "Value" field. Leave the other fields as default and click on "Create."
8. Create a subdomain and hosted zone for the demo AWS account by repeating steps 5-7, replacing "dev" with "prod."
