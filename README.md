# Datashades v2.0 CloudFormation templates

This repository contains the CloudFormation templates used to provision infrastructure for new Datashades stacks.

## 1: VPCs

This template will create one or more VPCs with subnets and other related components. Because a brand new AWS account already comes with a VPC it's recommended you keep this for use as your Production VPC and use this template to create a UAT and/or DEV VPC.

## 2: Stack

*Note: Before using this template, ensure you have created an SSH Key Pair via the EC2 console.*

This stack template creates the underlying resources you'll need for your CKAN stack. The template will provision a DEV/UAT/PROD stack and name the resources appropriately. If you require multiple stack types, re-use the template and select the appropriate options.

The following resources will be created:

* An EC2 instance for the CKAN services
* An EC2 instance for the web components
* A Route53 hosted zone (optional)
* An IAM role for EC2 permissions (required, unless a role named "AutoManage" already exists in the account)
* An RDS (optional)
* An Elastic Load Balancer (optional)
* An Elastic File System (optional)

# Next steps

Once your stack has been created you can set up the instances manually, or utilise the Ansible playbook and roles [here](https://git.links.com.au/Datashades/ansible).
