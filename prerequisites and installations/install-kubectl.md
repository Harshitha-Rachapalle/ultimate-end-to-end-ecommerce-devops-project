# kubectl
**kubectl** is basically a kubernetes command line tool which is used to interact with kubernetes API server.

official documentaion (https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/)

# Install kubectl binary with curl on Linux
**1.Download the latest release of kubectl**
```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
```
**2.Validate the binary by using**
```
ls
```
the output should be **kubectl**

### Download the kubectl checksum file:

```
 curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"
```
**Validate the kubectl binary against the checksum file:**
```
echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check
```
checksum file is mostly useful when somebody tries to hack the kubernetes cluster by putting out a wrong  kubectl file/binary

**3.Install kubectl**

```
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
```
**4.Test to ensure the version you installed is up-to-date:**
```
kubectl version --client
```
when we run **kubectl version** we can able to see both **client version  and server version**

when someone asks **k8s version** we should always say **server** version
when someone asks **kubectl version** we should always say **client** version


