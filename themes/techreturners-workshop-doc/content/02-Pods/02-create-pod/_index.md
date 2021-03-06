+++
menutitle = "Create a Pod - Declarative"
date = 2018-12-29T17:15:52Z
weight = 2
chapter = false
pre = "<b>- </b>"
+++

# Pod - Declarative Way

After completing this session , you will be able to create Pod declaratively.

Lets get started.

#### Lets Check the running Pods

```shell
k8s@k8s-master-01:~$ kubectl get pods
No resources found.
k8s@k8s-master-01:~$
```
Nothing 

#### Lets create one using a `YAML` file

```shell
$ vi pod.yaml
```

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: coffee-app
spec:
  containers:
  - image: ansilh/demo-coffee
    name: coffee
```

#### Apply YAML using `kubectl` command

```shell
$ kubectl apply -f pod.yaml
```

#### View status of Pod

Pod status is `ContainerCreating`
```shell
$ kubectl get pods
```
Output
```console
NAME         READY   STATUS              RESTARTS   AGE
coffee-app   0/1     ContainerCreating   0          4s
```

#### Execute `kubectl get pods` after some time
Now `Pod` status will change to `Running`

```shell
$ kubectl get pods
```
Output
```console
NAME         READY   STATUS    RESTARTS   AGE
coffee-app   1/1     Running   0          27s
```

#### Port forward to access the app
```shell
$ kubectl port-forward pod/coffee 9090
```

go to http://localhost:9090/ 



#### Delete pod
```shell
$ kubectl delete pod coffee-app
```

```console
pod "coffee-app" deleted
```

#### Make sure not pod is running 
```shell
$ kubectl get pods
```
