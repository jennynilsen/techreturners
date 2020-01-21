+++
menutitle = "Hands on"
date = 2018-12-29T17:15:52Z
weight = 3
chapter = false
pre = "<b>- </b>"
+++

# Pod - Declarative Way

After completing this session , you will be able to create Pod declaratively.

#### Lets Check the running Pods

```shell
k8s@k8s-master-01:~$ kubectl get pods
No resources found.
k8s@k8s-master-01:~$
```
Nothing <i class="fa fa-frown"></i>

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
  - image: ansilh/democoffee
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
What is the `pod` status?

```shell
$ kubectl get pods
```
Output
```console
NAME         READY   STATUS         RESTARTS   AGE
coffee-app   0/1     ErrImagePull   0          6s
```

What does describing the pod tell you?

#### Describe the pod to identify what the issue is
```shell
$ kubectl describe pod coffee-app
```
Can you docker pull the image?
```shell
$ docker pull ansilh/democoffee
```

Can you determine what the issue is?
If so correct the issue and try again

#### Verify the status of Pod
```shell
$ kubectl get pods -o wide
```

```console
NAME         READY   STATUS    RESTARTS   AGE   IP            NODE                 NOMINATED NODE   READINESS GATES
coffee-app   1/1     Running   0          9s    10.244.0.28   kind-control-plane   <none>           <none>
```

#### Use Port Forward to access the app

```shell
kubectl port-forward pod/coffee-app 9090
```

Go to http://localhost:9090/ 


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

