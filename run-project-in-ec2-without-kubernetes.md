# run project locally that means in ec2 using docker compose

After completing all prerequisites, check docker compose using below command
```
docker compose -h
```
## Docker compose
**..>** when we are dealing with multiple microservices, organizations prefer docker compose to run locally.
**..>** Docker compose can run multiple containers at once and it can also establish the dependencies between containers( i.e which should run first , last etc suppose db first, then back end, then front end)
using docker compose we can **build the images, run the containers, create networks, volumes**

I have forked code from oprntelemetry demo github from google
Now, copy the github code and clone it
```
git clone https://github.com/Harshitha-Rachapalle/project-opentelemetry-demo.git
```
```
cd project-opentelemetry-demo/
```
```
ls -ltr
```
in this we have docker-compose.yml   inside this we have networks, services, containers

Now run the below command which pull all the images

```
docker compose up
```
# Challenges and it's solution
when we get this issue **write /var/lib/docker/tmp/GetImageBlob2376640635: no space left on device**
i.e reason is  storage is less so, we need to resize this volume and file system  then this issue will issolve

in my case, i am using t2.large. In ec2 instance under storage i have volume size is 8 gb which is not sufficient . I need to increase to 30 gb 

To check disc space
```
df -h
```

## solution
**step 1**: modify the volume size
> go to ec2 instance
> click on storage
> select volume id
> click on modify and increase the size to 30 gb and click save
Now after some time we need to check volume state as **in-use**

To check blocks available in our system 
```
lsblk
```
**xvda** this block typically used when virtualization of type **xen**
xvda1 is mounted on / where as in df -h command /dev/root is also mounted on / now we need to resize this to 30 gb
**step 2**: resize partition (xvdal)
```
sudo growpart /dev/xvda 1
```
```
lsblk
```
we can see xvda1 size is 29gb whereas in df-h it is not updated for resize in diskspace we use below command

```
sudo resize2fs /dev/xvda1
```
now if we run df -h the size has been increased to 29 gb

now storage problem has beeb resolve

## now continue the task with below command
```
docker compose up
```

#  AWS Security groups
> in aws , for every instance there will be a security group
> Security group acts as a firewall which doesn't allow inbound traffic to instance
> security groups block the traffic whereas NACL will allow traffic

**To allow traffic**
In an instance, go to security group , edit inbound rules,add rule > all traffic> anywhere

## finally we are able to access the opentelemetry application buy using ipaddress:8080









