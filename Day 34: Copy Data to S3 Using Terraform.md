## Task
The Nautilus DevOps team is presently immersed in data migrations, transferring data from on-premise storage systems to AWS S3 buckets. 
They have recently received some data that they intend to copy to one of the S3 buckets.

S3 bucket named `datacenter-cp-30891` already exists. Copy the file /tmp/datacenter.txt to s3 bucket datacenter-cp-30891 using Terraform.

## Solution
Check the resource
<img width="460" height="72" alt="image" src="https://github.com/user-attachments/assets/8aed1602-5043-45b0-8602-113ee84038cf" />

in main.tf
<img width="443" height="356" alt="image" src="https://github.com/user-attachments/assets/811b4fac-11fa-4b2a-ae48-3fc400f7189d" />

```
terraform init
terraform plan
terraform apply
```
<img width="439" height="280" alt="image" src="https://github.com/user-attachments/assets/607c84b9-c03b-450e-a469-aa944cc5c6b3" />


