# This is the GitHub repo to showcase my work on AWS 
## Chapter1: AWS CLI/CloudFormation
 
  In this Chapter, I will create the labs to show the AWS resource creation through AWS CLI and CloudFormation.

1. The below is the command to create VPC through AWS CLI: 

Command: 
```
          aws ec2 create-vpc \
              --cidr-block 10.0.0.0/16 \
              --tag-specifications 'ResourceType=vpc,Tags=[{Key=Name,Value=MyVpc}]'
```
Sample output: 

```
{
    "Vpc": {
        "CidrBlock": "10.0.0.0/16",
        "DhcpOptionsId": "dopt-0db3c6bf7d3d3d338",
        "State": "pending",
        "VpcId": "vpc-0258ffd84df5aa130",
        "OwnerId": "12345678912",
        "InstanceTenancy": "default",
        "Ipv6CidrBlockAssociationSet": [],
        "CidrBlockAssociationSet": [
            {
                "AssociationId": "vpc-cidr-assoc-0c6649348aed21487",
                "CidrBlock": "10.0.0.0/16",
                "CidrBlockState": {
                    "State": "associated"
                }
            }
        ],
        "IsDefault": false,
        "Tags": [
            {
                "Key": "Name",
                "Value": "MyVpc"
            }
        ]
    }
}
```

The above command shows the VPC state in pending, to check the VPC state later, please use the below command: 

```
aws ec2 describe-vpcs --vpc-ids <vpc-id>
```
Sample output: 
```
aws ec2 describe-vpcs --vpc-ids vpc-0258ffd84df5aa130

{
    "Vpcs": [
        {
            "CidrBlock": "10.0.0.0/16",
            "DhcpOptionsId": "dopt-0db3c6bf7d3d3d338",
            "State": "available",
            "VpcId": "vpc-0258ffd84df5aa130",
            "OwnerId": "1234567812",
            "InstanceTenancy": "default",
            "CidrBlockAssociationSet": [
                {
                    "AssociationId": "vpc-cidr-assoc-0c6649348aed21487",
                    "CidrBlock": "10.0.0.0/16",
                    "CidrBlockState": {
                        "State": "associated"
                    }
                }
            ],
            "IsDefault": false,
            "Tags": [
                {
                    "Key": "Name",
                    "Value": "MyVpc"
                }
            ]
        }
    ]
}
```

2. The below is the command to delete the VPC 

```
aws ec2 delete-vpc --vpc-id <vpc-id>
```

