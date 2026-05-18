## Task
The Nautilus DevOps team is automating IAM user creation using Terraform for better identity management.

For this task, create an AWS IAM User using Terraform with the following requirements:

The IAM User name `iamuser_mark` should be stored in a variable named KKE_user.

## Solution
In variable.tf
```
variable "KKE_user" {
    default = "iamuser_mark"
    type = string
    description = "Name of the IAM user."
}
```

In main.tf
```
resource aws_iam_user "iam_user" {
    name = var.KKE_user

    tags = {
    Name = var.KKE_user
  }
}
```
<img width="686" height="177" alt="image" src="https://github.com/user-attachments/assets/181352cc-8d9a-4777-84c9-c9e0cf472bd5" />
