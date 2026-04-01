## Task
Data protection and recovery are fundamental aspects of data management. 
It's essential to have systems in place to ensure that data can be recovered in case of accidental deletion or corruption. 
The DevOps team has received a requirement for implementing such measures for one of the S3 buckets they are managing.

The S3 bucket name is `datacenter-s3-31575`, enable versioning for this bucket using Terraform.

## Solution
```
resource "aws_s3_bucket_versioning" "s3_versioning" {
  bucket = aws_s3_bucket.s3_ran_bucket.id
  versioning_configuration {
    status = "Enabled"
  }
}
```

```
terraform init
terraform plan
terraform apply
```

<img width="488" height="207" alt="image" src="https://github.com/user-attachments/assets/c142261c-807c-488a-95c2-f6caaca528c2" />

