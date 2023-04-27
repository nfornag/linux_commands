

## Linux Practice
<details>
<summary>File Management</summary>
    <br/>
    
ls - list files and folder
    
```bash
ls
```
cat - describe content of file
    
```bash
cat README.txt 
```
more - describe content of file
    
```bash
more README.txt 
```
tail 
```bash
tail -f README.txt
tail -100f README.txt
tail -10f README.txt 
```
cd - change directory
```bash
cd helloworld
```

touch - create an empty file
```bash
touch README.md
touch sample.txt

```
ssh 
```bash
ssh -i demo-ec2-01.pem ubuntu@10.7.1.87
```
scp 
```bash
scp -r eks-vpc/ root@10.7.1.87:/opt
```
```bash
ag@ce-book ~/.ssh $ pwd
/home/nag/.ssh
nag@ce-book ~/.ssh $ more config
Include configs/*

Host white-jh
    User                   ubuntu 
    HostName               54.236.231.92
    Port                   22
    IdentitiesOnly         yes
    IdentityFile           ~/.ssh/id_rsa
    UserKnownHostsFile     /dev/null
    StrictHostKeyChecking  no
    PasswordAuthentication no
    TCPKeepAlive           yes
    
nag@ce-book ~/.ssh $ cd configs/
nag@ce-book ~/.ssh/configs $ ls -ltr
nag@ce-book ~/.ssh/configs $ more ce-white-config 

Host demoec201
    User                   ubuntu
    HostName               10.7.1.52
    ProxyJump              white-jh
    Port                   22
    IdentitiesOnly         yes
    IdentityFile           /home/nag/Downloads/demo-ec2-key.pem
    UserKnownHostsFile     /dev/null
    StrictHostKeyChecking  no
    PasswordAuthentication no
    TCPKeepAlive           yes
nag@ce-book ~/.ssh/configs $ 
```
find

find a file which name sample.txt

```bash
find ./ -name sample.txt
```
</details>

<details>
<summary>User Management</summary>
    <br/> 
    
</details>

<details>
<summary>Access Management</summary>
     <br/>
</details>

<details>
<summary>Configuration Management</summary>
 <br/>
</details>

### [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-welcome.html) 


<details>
<summary>Example Commands</summary>
    
    
Export AWS credentials in Terminal
```bash
export AWS_ACCESS_KEY_ID=AKIAIOSFODNN7EXAMPLE
export AWS_SECRET_ACCESS_KEY=wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
export AWS_DEFAULT_REGION=us-east-1
```

Describe EC2 Instances
```bash
aws ec2 describe-instances
```
List S3 Buckets
```bash
aws s3 ls
```
Create an S3 Bucket

```bash
aws s3api create-bucket --bucket test-bucket-948489282 --region us-east-1
```
Delete an S3 Bucket
```bash
aws s3api delete-bucket --bucket test-bucket-948489282 --region us-east-1
```
Create an EC2 Instance
```bash
aws ec2 run-instances --image-id ami-007855ac798b5175e --count 1 --instance-type t2.micro --key-name test-ec2 
```
Delete an EC2 Instance
```bash
aws ec2 terminate-instances --instance-ids i-394jd83kdujd83jdh7
```
</details>

## Docker

<details>
<summary>Docker Commands</summary>
      <br/>
</details>
<details>
<summary>Docker Swarm Commands</summary>
      <br/>
</details>

