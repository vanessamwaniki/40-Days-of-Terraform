## Task
The Nautilus DevOps team is strategizing the migration of a portion of their infrastructure to the AWS cloud. 
As part of this phased migration approach, they need to allocate an Elastic IP address to support external access for specific workloads.

For this task, create an AWS Elastic IP using Terraform with the following requirement:

The Elastic IP name `xfusion-eip` should be stored in a variable named `KKE_eip`. The Terraform working directory is `/home/bob/terraform`.

Note:
The configuration values should be stored in a variables.tf file.

The Terraform script should be structured with a main.tf file referencing variables.tf.

## Solution
In variables.tf
```
variable "KKE_eip" {
    description = "Elastic IP name"
    type = string
    default = "xfusion-eip"
}
```

In main.tf
```
resource "aws_eip" "this" {
    domain = "vpc"
    tags = {
        Name = var.KKE_eip
    }
}
```

```
terraform init
terraform plan
terraform apply
```
<img width="491" height="434" alt="image" src="https://github.com/user-attachments/assets/33ae06ed-4a4a-4d48-8e90-2a915505ffeb" />
