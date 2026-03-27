## Task
There is an instance named devops-ec2 and an elastic-ip named devops-ec2-eip in us-east-1 region. 
Attach the devops-ec2-eip elastic-ip to the devops-ec2 instance using Terraform only. 

## Solution
Add the Elastic Ip association Terraform code in main.tf
<img width="558" height="363" alt="image" src="https://github.com/user-attachments/assets/63d05f4c-0286-475c-b7d8-bb6abcf3c3fb" />
<img width="587" height="311" alt="image" src="https://github.com/user-attachments/assets/710845fa-4526-447f-bb14-d73aeaa01133" />

```
terraform init
terraform plan
terraform apply
terraform show
```
<img width="533" height="183" alt="image" src="https://github.com/user-attachments/assets/f358a982-92d8-4ff6-87fe-2bd888258cb1" />


