## Task
The Nautilus DevOps team is enhancing infrastructure automation and needs to provision a Security Group using Terraform with specific configurations.

For this task, create an AWS Security Group using Terraform with the following requirements:

The Security Group name datacenter-sg should be stored in a variable named KKE_sg.
Note:
1. The configuration values should be stored in a variables.tf file.

2. The Terraform script should be structured with a main.tf file referencing variables.tf.

## Solution
In variable.tf
```
variable "KKE_sg" {
    description = "Name for security group"
    type = string
    default = "datacenter-sg"
}
```

In main.tf
```
resource "aws_security_group" "this" {
  name        = var.KKE_sg
  description = "Security group for Nautilus environment"

  # Ingress rule: Allow SSH access
  ingress {
    description = "Allow SSH"
    from_port   = 22
    to_port     = 22
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }

  # Egress rule: Allow all outbound traffic
  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }

  tags = {
    Name = var.KKE_sg
  }
}
```
Terraform
```
terraform init
terraform plan
terraform apply
```
<img width="339" height="91" alt="image" src="https://github.com/user-attachments/assets/cc71c163-313f-4601-9536-2d2e1e0704bc" />

