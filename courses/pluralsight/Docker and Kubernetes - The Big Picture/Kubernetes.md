## History

Google was running tons of apps inside [[Intro#What is a Container?|containers]] and to handle a big amount of containers, they had to create internal tools. Then Google created Kubernetes, a open-source tool featured in CNCF (Cloud Native Computing Foundation).

## What k8s can do?

Kubernetes can handle common situations that can come with big applications. e.g.: Autoscaling, Health monitoring, Scheduling, etc.

Kubernetes run in a cluster of machines, we have the Control Plane and Worker Nodes. The control plane takes the decisions of what to run, what to stop, what to scale, etc. The worker nodes runs containers with apps.