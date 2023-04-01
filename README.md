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
