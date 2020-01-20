+++
menutitle = "Services Introduction"
date = 2018-12-29T17:15:52Z
weight = 1
chapter = false
pre = "<b>- </b>"
+++

#### What is a Service in Kubernetes?

A Service enables network access to a set of Pods in Kubernetes.

Services select Pods based on their labels. When a network request is made to the service, it selects all Pods in the cluster matching the service's selector, chooses one of them, and forwards the network request to it.

#### Kubernetes Service vs Deployment

What's the difference between a Service and a Deployment in Kubernetes?

## A deployment is responsible for keeping a set of pods running.

## A service is responsible for enabling network access to a set of pods.

We could use a deployment without a service to keep a set of identical pods running in the Kubernetes cluster. The deployment could be scaled up and down and pods could be replicated. Each pod could be accessed individually via direct network requests (rather than abstracting them behind a service), but keeping track of this for a lot of pods is difficult.

We could also use a service without a deployment. We'd need to create each pod individually (rather than "all-at-once" like a deployment). Then our service could route network requests to those pods via selecting them based on their labels.

Services and Deployments are different, but they work together nicely.
