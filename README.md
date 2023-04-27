# linux_commands

* ls 

Ex:
```bash
ls
```


* cat

Ex: 

```bash
cat README.txt 
```


more 

Ex: 
```bash
more README.txt 
```

tail:

Ex: 
```bash
tail -f README.txt
tail -100f README.txt
tail -10f README.txt 
```

cd

Ex
```bash
cd helloworld
```

touch

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

# Linux Commands

### awscli commands

* [Export AWS credentials in Terminal](https://github.com/ynraju4/cka-concepts/blob/master/docs/Application-Lifecycle-Management.md)


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
Create and EC2 Instance
```bash
aws ec2 run-instances --image-id ami-0688ba7eeeeefe3cd --count 1 --instance-type t2.micro --key-name test-ec2 
```
