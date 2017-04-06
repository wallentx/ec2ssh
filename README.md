# ec2ssh

ec2ssh is a tool that utilizes the [fzf](https://github.com/junegunn/fzf)
fuzzy matcher, and the [ec2-fzf](https://github.com/wallentx/ec2-fzf) tool in order to retrieve the public or private address of an ec2
instance.

## Installation

```
Download https://github.com/wallentx/ec2ssh/releases/download/1.0/release-1.0.tar.gz to a directory
Extract files
Run install.sh as sudo
Must have ~/.aws directory and credentials all set up
```

## Usage

Usage: ec2ssh [OPTIONS] STRING

    Description: List and parse through EC2 instances to connect to via SSH, or display private IP.

    OPTIONS:
        -l      Do not connect, and print private IP of instance
        -f      You can add filters on to the instances that are listed with the `-f`
                flag. You can define `-f` multiple times to filter by more than one
                value. Valid values are those used in the aws-sdk-go sdk: 
                http://docs.aws.amazon.com/sdk-for-go/api/service/ec2/#DescribeInstancesInput
        -h      Show this message

TO-DO: You can also set `--region` and pass the ec2 region you would like to list
instances in. By default, the region is set to `us-east-1`
```
ec2ssh -f tag:realm=test -f tag:Name=Test
```
