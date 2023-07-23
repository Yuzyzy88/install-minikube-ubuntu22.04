# Install Minikube on Ubuntu 22.04 VM

Need to install:

1. Install Docker
1. Install Kubectl
1. Install Minikube

Requirement:

- VirtualBox 5.2 or higher
- 2 CPU or more
- 2GB of free memory
- 20GB of free disk space
- Internet connection

## Install Docker

1. Install **Docker**

```
curl -fsSL https://get.docker.com -o get-docker.sh

sudo sh ./get-docker.sh --dry-run
```

2. Add your user to the docker group

```
sudo usermod -aG docker <user>
```

## Install Kubectl

Install using native package management

1. Update the apt package index and install packages needed to use the Kubernetes apt repository:

```
sudo apt-get update && sudo apt-get install -y apt-transport-https
```

2. Download the Google Cloud public signing key:

```
curl -fsSL https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo gpg --dearmor -o /etc/apt/keyrings/kubernetes-archive-keyring.gpg
```

3. Add the Kubernetes apt repository:

```
echo "deb [signed-by=/etc/apt/keyrings/kubernetes-archive-keyring.gpg] https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list
```

4. Update apt package index with the new repository and install kubectl:

```
sudo apt-get update && sudo apt-get install -y kubectl
```

5. Test to ensure the version you installed is up-to-date:

```
kubectl version --client
```

## Install Minikube

To install the latest minikube **stable** release on **x86-64 Linux** using **binary download**

```
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64

sudo install minikube-linux-amd64 /usr/local/bin/minikube
```

Check minikube version:

```
minikube version
```


## Start Cluster
Start cluster using the docker driver:

```
minikube start --driver=docker
```
