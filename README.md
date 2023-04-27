

## Linux Practice
<details>
<summary>File Management</summary>
    <br/>
    
```bash
ls
ls -ltr
ll
cat README.txt 
more README.txt 
tail -f README.txt
tail -100f README.txt
tail -10f README.txt
mkdir helloworld
cd helloworld
touch README.md
touch sample.txt
vi sample.txt
```

find - find a file which name sample.txt

```bash
find ./ -name sample.txt
```
Compress old files

```bash
# Compress the files that were genereated before 01-March-2023
touch -t 202303010000 /tmp/2023-Mar-01-0000
find /var/log/nginx -type f ! -newer /tmp/2023-Mar-01-0000 | xargs gzip
```
Delete old files

```bash
# Remove files that were genereated before 01-Jan-2023
touch -t 202301010000 /tmp/2023-Jan-01-0000
find /var/log/nginx -type f ! -newer /tmp/2023-Jan-01-0000 | xargs rm
```
Move old files to another directory
```bash
find /var/log/nginx/ -mtime +7 -name "*.log" -exec mv "{}" /var/log/nginx_backup/ \;',
```
Compress old files
```bash
find /var/log/nginx/ -mtime +7 -name "*.log" -exec gzip "{}" \;',
```
Delete old files
```bash
find /var/log/nginx/ -mtime +7 -name "*.log" -exec rm "{}" \;',
```


</details>

<details>
<summary>User Management</summary>
    <br/> 
Create user with home directory

```bash
sudo useradd -s /bin/bash -d /home/nag -m nag
```
Enable root user password login
```bash
#!/bin/bash
sudo sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config
sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/' /etc/ssh/sshd_config
sudo service sshd restart
sudo sudo su -
echo 'root:mankdhur567Q' | chpasswd
```
</details>

<details>
<summary>Access Management</summary>
     <br/>
</details>

<details>
<summary>Configuration Management</summary>
 <br/>
 
Configure Hostname
```bash
#!/bin/bash
sudo hostnamectl set-hostname myappserver01 --static
sudo hostnamectl set-hostname myappserver01 --transient
sudo echo -e "preserve_hostname: true" >> /etc/cloud/cloud.cfg
sudo systemctl reboot
``` 

</details>

## [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-welcome.html) 


<details>
<summary>CLI Commands</summary>
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
Copy files to s3 bucket

```bash   
aws s3 cp nginx.log s3://raju-us-east-1-demos3/ec2data/
aws s3 cp nginx.log s3://raju-us-east-1-demos3
```
Copy folders to s3 bucket

```bash   
aws s3 cp --recursive logs s3://raju-us-east-1-demos3
```
</details>

## Docker

<details>
<summary>CLI Commands</summary>
 <br/>
 
#### Manager Docker Images and Containers
 
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
docker stop docker-nginx test-nginx dev-nginx myapp mydevapp
docker stop prod-nginx
docker rm mydevapp myapp prod-nginx dev-nginx test-nginx docker-nginx
docker images
docker rmi 806f89a70ff8 263083118061 080ed0ed8312 e499797894d5
docker run hello-world
docker logs hello-world 
```
    
#### Create Docker swarm cluster in master node

```bash
docker swarm init
```

#### Join worker nodes to Docker swarm cluster

```bash
docker swarm join --token SWMTKN-1-2hyn8v3qytkz23vlsd9or92n9843ugyjy45qhqoknmibj9599c-bo27ga0u57qql3jijku4i5m09 10.7.2.102:2377
```

#### Create and manage services in Docker swarm clouster

```bash
docker node ls
docker service create   --name blue-service   --publish published=8081,target=8080  --replicas 6 ynraju4/srv-blue:6
docker ps
docker service rm green-service
docker ps
docker service scale green-service=4
```
</details>

## Ansible

<details>
<summary>CLI Commands</summary>
 <br/>
    
Encrypt files with ansible-vault
```bash    
ansible-vault encrypt --vault-password-file $HOME/.secrets/vault_id dev-sales-ssh.pem
ansible-vault decrypt --vault-password-file $HOME/.secrets/vault_id dev-sales-ssh.pem
```  
    
</details>
