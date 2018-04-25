# AWS Provisioning Tool

This project this target to automate the AWS provisioning process for ec2 and route53

### Prerequisites

This code is tested with python2.7.14, addtional modules (prettytable, boto3, paramiko) are required which will be installed automaticlly.

Need to configure following at home directory
```
[For Linux and Mac]
~/.aws/config
```
```
[For Windows]
"%UserProfile%"/.aws/config
```

config file details
```
[default]
region=ap-southeast-1
output=json

```


### Installing

* I have tested working on Mac and Linux

* sudo pip install aws_toolkit==0.9

## How to use it

```
from awspackage import aws

myaws = aws.AWS("AWS_ID",
        	"AWS_KEY",
        	"ROUTE53_Domain",
        	"VM Access KEY full path")

myaws.main()

```

* AWS_ID refer to the AWS console ID
* AWS_KEY refer to the aws console secrect key
* ROUTE53_Domain refer to the domain name that registered to the AWS under the same account, eg. cjaiwenwen.com (Put dummy data if you dont have route53 service)
* VM ACCESS KEY full path refer to the local pem key path eg, /Users/cjaiwenwen/Desktop/chenjun.pem 

## What can the library could achieve

* Create instance on any region if the VPC has been already created
* Control the number of the VMs could provisioned
* Choose the AMI image
* Choose the subnets
* Choose the security group
* Modify the security group rules if need to be
* Choose the size of the VM
* Assign CNAME for the provisioned VM
* Continue ping the provisioned host
* SSH to the host to confirm accessible (need to add ssh incoming rule)


## Authors

* **Chen Jun** - *Initial work* - [CJAIWENWEN](https://github.com/cjaiwenwen)

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details






