## Task
The Nautilus DevOps team is automating IAM role creation using Terraform to streamline permissions management. 
As part of this task, they need to create an IAM role with specific requirements.

For this task, create an AWS IAM role using Terraform with the following requirements:

The IAM role name `iamrole_siva` should be stored in a variable named `KKE_iamrole`.

## Solution
In variables.tf
```
variable "KKE_iamrole" {
    default = "iamrole_siva"
    type = string
    description = "Name of the  IAM role"
}
```

In main.tf
```
resource "aws_iam_role" "iam_role" {
    name = var.KKE_iamrole

    assume_role_policy = jsonencode({
    Version = "2012-10-17"
    Statement = [
      {
        Effect = "Allow"
        Principal = {
          Service = "ec2.amazonaws.com"
        }
        Action = "sts:AssumeRole"
      }
    ]
  })

  tags = {
    Name = var.KKE_iamrole
  }
}
```

```
terraform init
terraform plan
terraform apply
```

<img width="700" height="181" alt="image" src="https://github.com/user-attachments/assets/b7f5c77c-73ca-48d1-92ee-82685c4e4fe0" />


