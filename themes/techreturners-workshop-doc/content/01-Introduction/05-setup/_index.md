+++
menutitle = "Setup"
date = 2018-12-29T17:15:52Z
weight = 5
chapter = false
pre = "<b>- </b>"
+++

# Setting up Kind cluster

#### Install Docker if you don't already have it 

```shell
$ brew cask install docker
```

#### Install Kubernetes in Docker (Kind)
```shell
$ brew install kind
```

#### Create a cluster
```shell
$ kind create cluster
$ kind get clusters
```

#### Create a namesapce
```shell
$ kubectl create namespace <name>
```

#### Delete the cluster
```console
$ kind delete cluster
```
