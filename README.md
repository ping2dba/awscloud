# This is the GitHub repo to showcase my work on AWS 
## Chapter1: AWS CLI/CloudFormation
 
  In this Chapter, I will create the labs to show the AWS resource creation through AWS CLI and CloudFormation.

1. The below is the command to create VPC through AWS CLI: 

```
          aws ec2 create-vpc \
              --cidr-block 10.0.0.0/16 \
              --tag-specifications ResourceType=vpc,Tags=[{Key=Name,Value=MyVpc}]
```