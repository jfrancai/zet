## What is a Container Runtime ?

2008 - cgroups invention
* *Linux Containers* are born (LXC) : a combination of namespaces and cgroups

2013 - Docker is born
* Docker is built on top of LXC stack. They added the concept of container images.

2015 - Cloud Native Computing Foundation (CNCF)
* Kubernetes v1.0
* The Open Container Initiative (OCI) is founded


> runC is the result of all of Docker's work on libcontainer and the OCI. It is the de-facto standard low-level container runtime. It is written in Go and maintained under Docker's open source moby project.

* CRI : The container runtime interface

More details : [Demystifying Containers - Part II: Container Runtimes](https://medium.com/@saschagrunert/demystifying-containers-part-ii-container-runtimes-e363aa378f25), [cloud native landscape](https://landscape.cncf.io/serverless), [Open Container Initiative](https://opencontainers.org/about/overview/), [Runtime Specification](https://github.com/opencontainers/runtime-spec), [A Comprehensive Container Runtime Comparison](https://www.capitalone.com/tech/cloud/container-runtime/)

    #container #docker
