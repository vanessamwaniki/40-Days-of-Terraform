## Task
An IAM user named `iamuser_james` and a policy named `iampolicy_james` already exists. 
Use Terraform to attach the IAM policy `iampolicy_james` to the IAM user `iamuser_james`. 

## Solution
```
# Attach IAM policy to IAM user
resource "aws_iam_user_policy_attachment" "attach_policy" {
  user       = aws_iam_user.user.name
  policy_arn = aws_iam_policy.policy.arn
}
```

```
terraform init
terraform plan
terraform apply
terraform show
```
<img width="513" height="144" alt="image" src="https://github.com/user-attachments/assets/b7c0ff28-2270-4c5b-a854-370f15078890" />
