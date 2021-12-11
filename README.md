# Creating-a-DRY-Terraform-Environment-with-Terragrunt-in-Azure
Creating DRY Terraform Environments with Terragrunt in Azure
Creating a DRY Terraform Environment with Terragrunt in Azure
Introduction
Copy/pasting Terraform code between environments creates more opportunities for error as well as unnecessary time. With Terragrunt and DRY principles, a new approach can be taken to achieve very little infrastructure code, where developers can focus on modifying just the properties that matter. here will use Terragrunt to deploy a new environment by copying a DRY Terraform configuration and updating just the components that need to be changed.
The Terraform project is split into a directory for each component, the Resource Group (RG), Network, and Server. However, the Terraform configuration for each component contains a single terragrunt.hcl file that contains all the values for customizing that component. By using Terragrunt, see the configuration for each environment is slimmed down.

Notice there is an environment_vars.yaml file at the root of the directory. This file contains the important configuration data for customizing the environment which will be used in each subfolder to make the Terraform configurations DRY ( Don't Repeat Yourself).
Using Terragrunt with remotely sourced modules and locals allows developers to deploy a new version of the environment by modifying a single file. A traditional Terraform configuration environment not using Terragrunt would require each a .tfvars file to be modified for each configuration directory.
In short Terragrunt to quickly spin up a development environment from an existing production environment by copying the Terragrunt configuration and modifying a single file. 
 
 
