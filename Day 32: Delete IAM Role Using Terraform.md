## Task
Delete the IAM role named iamrole_jim using Terraform. Make sure to keep the provisioning code, as we might need to provision this instance again later.

## Solution
In main.tf

<img width="455" height="414" alt="image" src="https://github.com/user-attachments/assets/24b509b3-1ea9-4213-81c6-c771bed53bfb" />

```
terraform init
terraform destroy -target=aws_iam_role.role
terraform show
```
<img width="410" height="97" alt="image" src="https://github.com/user-attachments/assets/47ef4e68-f919-4c25-a1d7-1efa487a5ffb" />

## Notes:
1. Using -target flag
- Best Practice: Always run a terraform plan -destroy first to preview exactly what will be removed.
- If other resources depend on the one you are destroying, Terraform will also destroy those dependent resources. 

2. Deleting from Configuration (Recommended)
- Because Terraform is a "desired state" tool, the standard way to remove a resource is to delete its code from your .tf files. 
- Step 1: Delete or comment out the specific resource block in your Terraform file.
- Step 2: Run terraform apply.
- Result: Terraform identifies that the resource is missing from the configuration but exists in the state, so it generates a plan to destroy only that resource. 

3. Using the removed Block (Modern Approach)
- Starting with Terraform v1.7+, you can use the removed block to gracefully handle resource deletion.
- Setting `destroy = false` allows you to remove a resource from Terraform’s state while ensuring the real infrastructure object remains intact.
- Replace your resource block with:
```
removed {
  from = aws_instance.example
  lifecycle {
    destroy = true
  }
}
```
- Run terraform apply to execute the destruction. This is safer than just deleting code because it explicitly documents the removal in your configuration. 
