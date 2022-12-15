## Big picture

Kubernetes runs in a cluster, inside the cluster we have master nodes and worker nodes. Usually these master nodes are called the *control plane*. We can package and describe how our application should run and give to the control plane, then the control plane handle all the work to run your app inside the worker nodes.

## Masters or Control Plane

They are the intelligence of the cluster and in production, they are supposed to be available always. It is important to have an odd number of master nodes, so we don't have to deal with a deadlock situation called "split brain". Every master node runs every master component.

### Split brain (deadlock)

This situation is caused when the master nodes can't ensure if they can communicate with the majority of nodes, so the cluster enters in read-only state.

## Components
### ApiServer
It's the front-end to the control plane, so every time we need to communicate with our cluster, we use the `apiserver`. A REST API is exposed and this API consumes JSON and YAML.
### Cluster Store
The cluster store it's the place where Kubernetes persists cluster state and config. It's based on *etcd*, a key-value pair distributed database.
### Controller Manager
It's a component that has o lot of controllers inside and it's responsible for updating the cluster state to match the **desired state** defined by the user. 
### Scheduler
It's responsible for assigning work to cluster nodes. It's a very complex component.

![[BigPicture.png]]

## Worker Nodes
## Components
### Kubelet
It's the main agent of all the nodes. It's responsible to watch the API Server for work, execute pods and report back to Masters.
### Container Runtime
It's responsible for running and stopping containers. Can be Docker, but it's possible to plug other runtime if needed, for example *containerd*. 
### Kube-proxy
It's a network component and it's responsible for giving every Pod a IP address. Can be used as basic load-balancer using Services.

## Declarative Model

Kubernetes works using a declarative model, this means that we can declare de the state that we want in our infrastructure and Kubernetes will find a way to keep our cluster in that **desired state**. For Kubernetes, it's very important that the Observer State matches the Desired State.

## Pod

It's the atomic component of Kubernetes. You can run multiple containers inside a Pod. Every Pod is a execution environment, so containers running inside that Pod can share resources like IP addresses and file system. For the most part of the time we want to run one container per Pod.

## Services

It's a component that has a stable name and IP, different from Pods, that every new Pod has a new IP. So we can use a Service to deal with network calls and basic load-balancing. Services can identify the Pods that it needs to manage using Labels. Services only sends traffic for healthy Pods.

![[Services.png]]

## Deployments

A Deployment is a component that acts as an abstraction with advanced features for Pods, like self-healing and rollbacks. Deployments are for stateless apps. Deployment -> ReplicaSet -> Pod -> Containers


