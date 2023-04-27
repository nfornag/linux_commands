

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
    <br/> 
    
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
 
```bash
docker images
docker pull nginx
docker images
docker run --name docker-nginx -p 80:80 nginx
docker run --name docker-nginx -p 80:80 -d nginx
docker ps -a 
docker rm 15748c592407 22f7a8be6d72 7a31e0f8f07a 9cefe4632514
docker run --name docker-nginx -p 80:80 -d nginx
docker ps -a
docker run --name test-nginx -p 8000:80 -d nginx
docker run --name dev-nginx -p 8001:80 -d nginx
docker run --name prod-nginx -p 8005:80 -d nginx
docker exec -it test-nginx /bin/bash
docker images 
docker ps 
docker ps -a
docker stop docker-nginx test-nginx dev-nginx myapp mydevapp
docker stop prod-nginx
docker rm mydevapp myapp prod-nginx dev-nginx test-nginx docker-nginx
docker images
docker rmi 806f89a70ff8 263083118061 080ed0ed8312 e499797894d5
docker run hello-world
```
</details>
<details>
<summary>Docker Swarm Commands</summary>
<br/>
</details>

