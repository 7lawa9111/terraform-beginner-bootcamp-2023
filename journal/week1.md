<<<<<<< HEAD

=======
# Terraform Beginner Bootcamp 2023 - Week 1

## Root Module Structure

Our root module structure is as follows:

```
PROJECT_ROOT
│
├── main.tf                 # everything else.
├── variables.tf            # stores the structure of input variables
├── terraform.tfvars        # the data of variables we want to load into our terraform project
├── providers.tf            # defined required providers and their configuration
├── outputs.tf              # stores our outputs
└── README.md               # required for root modules
```

[Standard Module Structure](https://developer.hashicorp.com/terraform/language/modules/develop/structure)

## Terraform and Input Variables

### Terraform Cloud Variables

In terraform we can set two kind of variables:
- Enviroment Variables - those you would set in your bash terminal eg. AWS credentials
- Terraform Variables - those that you would normally set in your tfvars file

We can set Terraform Cloud variables to be sensitive so they are not shown visibliy in the UI.

### Loading Terraform Input Variables

[Terraform Input Variables](https://developer.hashicorp.com/terraform/language/values/variables)

### var flag
We can use the `-var` flag to set an input variable or override a variable in the tfvars file eg. `terraform -var user_ud="my-user_id"`

### var-file flag

The -var flag is used to pass values for Input Variables to Terraform commands. This flag can be used with both of the Terraform plan and apply commands. The argument passed to the -var flag is a string surrounded by either single or double quotes.

### terraform.tvfars

This is the default file to load in terraform variables in blunk

### auto.tfvars

tfvars" file is an alternative to using the "-var" flag or environment variables. The file defines the variable values used by the script. If the file is named "terraform. tvars" it is loaded by default. It's important these files don't get checked into source control, or you are potentially exposing sensitive data.

### order of terraform variables

* Environment variables (TF_VAR_variable_name)
* The terraform.tfvars file.
* The terraform.tfvars.json file.
* Any . auto. tfvars or . auto. tfvars. ...
* Any -var and -var-file options on the command line, in the order they are provided.
* Variable defaults.

