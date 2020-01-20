+++
menutitle = "Docker"
date = 2018-12-29T17:15:52Z
weight = 1
chapter = false
pre = "<b>- </b>"
+++


# What is Docker

### Back to Basics - Containers

##### What is a container image?
A lightweight, stand-alone, executable package of a piece of software that includes everything needed to run it: code, runtime, system tools, system libraries, settings.

- Read-only templates from which a container is instantiated
- Like a stopped Virtual Machine
- Docker images are made up of layers
- Layers are ordered by priority
- Layers are merged to create the image
- Each layer corresponds to line in a Dockerfile

##### What does Docker do?
- Allows you to develop, ship and run applications through containers
- Collects the pieces into an easy package 
- Frees developers to write code without worrying about the system
- Gives systems flexibility and small footprints

##### Why have containers replaced VMs?
- VMs run on physical hardware
- Containers run in user space 
- VMs require a lot of overhead
- Containers run natively 
- Both provide isolated environments

##### What to do when you have lots of containers?
- Orchestration is scheduling jobs to maximize resources and uptime. This needs to be reactive to changes in demand.
- Orchestrators are keyed into what is available. They react quickly to changes in resources, needs, or environment. 
 
##### What are the orchestrators?

- Docker Swarm from Docker
- Kubernetes from Google
- Mesos  from Apache
- Nomad from Hashicorp
- OpenShift by RedHat
- PaaS from Amazon, Azure or Google, ...

### Kubernetes?!









# What is Docker
Docker is a tool designed to make it easier to create, deploy, and run applications by using containers. Containers allow a developer to package up an application with all of the parts it needs, such as libraries and other dependencies, and ship it all out as one package.

In a way, Docker is a bit like a virtual machine. But unlike a virtual machine, rather than creating a whole virtual operating system, Docker allows applications to use the same Linux kernel as the system that they're running on and only requires applications be shipped with things not already running on the host computer. This gives a significant performance boost and reduces the size of the application.

![Kernel](docker.jpg)
