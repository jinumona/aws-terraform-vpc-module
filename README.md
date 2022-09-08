
# Terraform-VPC-Module

Terraform module to create VPC on any region

## variables on module

```bash

variable "project" {
    default = "sample"
}

variable "env" {
    default = "test"
}

variable "vpc_cidr" {
    default = "172.16.0.0/16"
}

```

## Variables to passing to the VPC module

```bash
  module "vpc" {

 source  = "Absolute path of the directory in which the module is present"
 vpc_cidr= "cidr of the vpc you need to create"
 project = "Name of the project"
 env     = "Name of the environmet eq:- production,testing,development.."

}
```

## Output from the module

```bash
output "vpc_id" {
    value = aws_vpc.vpc.id
}

output "public1_subnet_id" {
    value= aws_subnet.public1.id
}

output "public2_subnet_id" {
    value= aws_subnet.public2.id
}

output "public3_subnet_id" {
    value= aws_subnet.public3.id
}

output "private1_subnet_id"{
    value = aws_subnet.private1.id
}

output "private2_subnet_id"{
    value = aws_subnet.private2.id
}

output "private3_subnet_id"{
    value = aws_subnet.private3.id
}

```


## Calling output from the VPC module to the project

```bash

module.vpc.private1_subnet_id
module.vpc.private2_subnet_id
module.vpc.private3_subnet_id
module.vpc.public1_subnet_id
module.vpc.public2_subnet_id
module.vpc.public3_subnet_id
module.vpc.vpc_id
}
```
