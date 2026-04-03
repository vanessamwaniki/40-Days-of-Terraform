## Task
A S3 bucket named nautilus-bck-27752 already exists.

1) Copy the contents of nautilus-bck-27752 S3 bucket to /opt/s3-backup/ directory on terraform-client host (the landing host once you load this lab).

2) Delete the S3 bucket nautilus-bck-27752.

3) Use the AWS CLI through Terraform to accomplish this task—for example, by running AWS CLI commands within Terraform.


## Solution
In main.tf file
```
resource "null_resource" "s3_backup_deletion" {
  provisioner "local-exec" {
    command = <<EOT
      echo "Creating backup directory..."
      mkdir -p /opt/s3-backup/

      echo "Copying contents from S3 bucket to local directory..."
      aws s3 cp s3://nautilus-bck-27752 /opt/s3-backup/ --recursive

      echo "Deleting the S3 bucket..."
      aws s3 rb s3://nautilus-bck-27752 --force
    EOT
  }
}
```

```
terraform init
terraform plan
terraform apply
```
<img width="516" height="353" alt="image" src="https://github.com/user-attachments/assets/9a5e3156-03c7-4f94-845d-e51ff2fed3a0" />
