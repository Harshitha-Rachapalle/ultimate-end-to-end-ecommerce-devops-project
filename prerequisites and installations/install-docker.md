# Docker Installation on Ubuntu EC2

we can use the official documentation to install docker (https://docs.docker.com/engine/install/ubuntu/)

# Install using the **apt** repository

**1. Set up Docker's apt repository.**
### Add Docker's official GPG key:
```
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
```

### Add the repository to Apt sources:
```
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```
**2.Install the Docker packages.**
```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

**3.Verify that the installation is successful by running the hello-world image:**
```
sudo docker run hello-world
```

Run
```
docker ps 
```
if we see output as permission denied then try with "**sudo**"

To resolve this issue like adding sudo everytime we have a solution below i.e in below command we r modifying/adding user to a group(aG). here ubuntu is a user and docker is a group

```
sudo usermod -aG docker ubuntu
```
if we run **docker ps** command still if it shows as a permission denied then try to logout and login 

**To check the images use below command**
```
docker images
```
