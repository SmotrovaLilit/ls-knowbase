# Container orchestrators
**Container** - an application-centric method to deliver high-performing, scalable application on any infrastructure. 
**Container image** -  bundles the application with its runtime, dependencies. 
Containers can be deployed from a specific image on many platforms, such as: workstations, virtual machines, public cloud etc. 

**Container orchestrators** are tools which group systems together to form clusters where containers' deployment and management is automated at scale while meeting the requirements:
- Fault-tolerance
- On-demand scalability
- Optimal resource usage
- Auto-discovery to automatically discover and communicate with each other
- Accessibility from the outside world
- Seamless updates/rollbacks without any downtime.

Container orchestratration tools
- [Amazon Elastic Container Service](https://aws.amazon.com/ecs/)  
    Amazon Elastic Container Service (ECS) is a hosted service provided by [Amazon Web Services](https://aws.amazon.com/) (AWS) to run containers at scale on its infrastructure.
- [Azure Container Instances](https://azure.microsoft.com/en-us/products/container-instances/#overview)  
    Azure Container Instance (ACI) is a basic container orchestration service provided by [Microsoft Azure](https://azure.microsoft.com/en-us/).
- [Azure Service Fabric](https://azure.microsoft.com/en-us/products/service-fabric/)  
    Azure Service Fabric is an open source container orchestrator provided by [Microsoft Azure](https://azure.microsoft.com/en-us/).
- [Kubernetes](https://kubernetes.io/)  
    Kubernetes is an open source orchestration tool, originally started by Google, today part of the [Cloud Native Computing Foundation](https://www.cncf.io/) (CNCF) project.
- [Marathon](https://mesosphere.github.io/marathon/)  
    Marathon is a framework to run containers at scale on [Apache Mesos](https://mesos.apache.org/) and [DC/OS](https://dcos.io/)
- [Nomad](https://www.nomadproject.io/)  
    Nomad is the container and workload orchestrator provided by [HashiCorp](https://www.hashicorp.com/).
- [Docker Swarm](https://docs.docker.com/engine/swarm/)  
    Docker Swarm is a container orchestrator provided by [Docker, Inc](https://www.docker.com/). It is part of [Docker Engine](https://docs.docker.com/engine/).
Most container orchestrators can:

- Group hosts together while creating a cluster.
- Schedule containers to run on hosts in the cluster based on resources availability.
- Enable containers in a cluster to communicate with each other regardless of the host they are deployed to in the cluster.
- Bind containers and storage resources.
- Group sets of similar containers and bind them to load-balancing constructs to simplify access to containerized applications by creating an interface, a level of abstraction between the containers and the client.
- Manage and optimize resource usage.
- Allow for implementation of policies to secure access to applications running inside containers.

The managed Kubernetes as-a-Service solution:
[Amazon Elastic Kubernetes Service](https://aws.amazon.com/eks/) (Amazon EKS), [Azure Kubernetes Service](https://azure.microsoft.com/en-us/products/kubernetes-service/#overview) (AKS), [DigitalOcean Kubernetes](https://www.digitalocean.com/products/kubernetes), [Google Kubernetes Engine](https://cloud.google.com/kubernetes-engine/) (GKE), [IBM Cloud Kubernetes Service](https://www.ibm.com/cloud/kubernetes-service), [Oracle Container Engine for Kubernetes](https://www.oracle.com/cloud/cloud-native/container-engine-kubernetes/), or [VMware Tanzu Kubernetes Grid](https://tanzu.vmware.com/kubernetes-grid).