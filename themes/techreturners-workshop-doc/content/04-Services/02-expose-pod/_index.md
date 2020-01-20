+++
menutitle = "Expose Pod"
date = 2018-12-29T17:15:52Z
weight = 2
chapter = false
pre = "<b>- </b>"
+++

# Expose service running on Pod.

#### Service

Services play a vital role in the world of kubernetes, they provide a stable endpoint and distribute traffic across pods. 

How can we expose a service to external world so that users can access it ? We need to `expose` the service.

![Pod](pod-service.png?classess=shadow)

In this section we will deploy a simple “echo server” application onto the cluster and expose the deployment using a NodePort service.

Deploy a simple “echo server” application onto the cluster
```shell
$ kubectl create deploy http-echo --image=gcr.io/google-containers/echoserver:1.10
```

Verify that the pods exist
```shell
$ kubectl get pods
```

Output:
```shell
NAME                        READY   STATUS    RESTARTS   AGE
http-echo-d458c6655-8n4x9   1/1     Running   0          12s
```

Is there a service?
```shell
$ kubectl get svc
```
Nope.

Expose the deployment using the service type NodePort. This setting makes the service visible outside the Kubernetes cluster by the node’s IP address and the port number declared in this property. 
```shell
$ kubectl expose deployment http-echo --type=NodePort --name=echo-service --port=8080
```

Verify that the service now exists
```shell
$ kubectl get svc -o wide
```

Lets describe the service to see how the mapping of Pods works in a service object. How many endpoints are there?
```shell
$ kubectl describe svc echo-service
```

Access the service
```shell
$ kubectl port-forward svc/echo-service 8080
```
```shell
$ curl 127.0.0.1:8080
```

Scale up the deployment
```shell
kubectl scale deployment http-echo --replicas=10
```

Check the status of the rollout 
```shell
$ kubectl rollout status
```

List the events to see everything that has just happened
```shell
$ kubectl get events
```

