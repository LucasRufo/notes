## The bad old days

Companies used to run one application per physical server, but this was bad, because no one had idea of how big should that server be. 
So we had a lot of apps running on powerful machines and consuming less than 20% of the CPU/memory.

But at some point, companies started using [[Virtual Machines]] and started running more than one app per server.

But, Virtual Machines had a [[Virtual Machines#Problem|problem]], you had to install a new Operating System for every VM, and every new OS consumes resources of the underlying machine. 

## What is a Container?

Containers are lightweight packages of your application code together with dependencies such as specific versions of programming language runtimes and libraries required to run your software services. (Definition from this website: [What are containers?  |  Google Cloud](https://cloud.google.com/learn/what-are-containers))

To use containers, you only need the underlying operating system, and containers can reuse resources and libraries from that OS. So, with containers you can save resources using a "minimal machine" and still be able to run multiple apps in one server.

You can start and kill containers pretty fast.




