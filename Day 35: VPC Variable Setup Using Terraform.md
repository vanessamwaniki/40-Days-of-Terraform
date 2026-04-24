## Task
The Nautilus DevOps team is automating VPC creation using Terraform to manage networking efficiently. As part of this task, they need to create a VPC with specific requirements.

For this task, create an AWS VPC using Terraform with the following requirements:

- The VPC name `devops-vpc` should be stored in a variable named `KKE_vpc`.

- The VPC should have a CIDR block of 10.0.0.0/16.

Note:

- The configuration values should be stored in a variables.tf file.

- The Terraform script should be structured with a main.tf file referencing variables.tf.


## Solution
In variables.tf
```
variable "KKE_vpc" {
  description = "The name of the VPC"
  type        = string
  default     = "devops-vpc"
}
```

In main.tf
```
resource "aws_vpc" "this" {
  cidr_block = "10.0.0.0/16"

  tags = {
    Name = var.KKE_vpc
  }
}
```
```
terraform init
terraform plan
terraform apply
```

<img width="451" height="414" alt="image" src="https://github.com/user-attachments/assets/c9736918-73c7-434a-8a03-2ca0c5798711" />

