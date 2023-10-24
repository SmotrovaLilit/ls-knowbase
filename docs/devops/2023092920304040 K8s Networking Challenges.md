#  Networking Challenges
- Container-to-Container inside Pods
- Pod-to-Pod communication on the same node and across cluster nodes
- Service-to-Pod communication within the same namespace and across cluster namespaces
- External-to-Service communication for clients to access applications in a cluster
## Container-to-Container
A network namespace can be shared:
- across containers
- with the host OS.
**Pause container** creates network namespace for the Pod.  Containers inside pod can talk to each other via localhost. [[2023100715543131 K8s Single IP per Pod]]
[[2023100717075151 K8s CNI]]
Each pod receives unique IP address(**IP-per-Pod**), like VMs are able to communicate with each other on the same network.
Communication between containers must be throw Container network interface (CNI) supported by [CNI plugins](https://github.com/containernetworking/cni#3rd-party-plugins).
Most CNI plugins are 3rd-party Software Defined Networking (SDN) solutions implementing the Kubernetes networking model. Examples of SDN:  [Flannel](https://github.com/coreos/flannel/), [Weave](https://www.weave.works/oss/net/), [Calico](https://www.tigera.io/project-calico/) 
![[Pasted image 20230929202821.png]]
## Pod-to-Pod Communication Across Nodes
The  requirement from Kubernetes was the following:
- All pods can communicate with each other across nodes.
- All nodes can communicate with all pods.
- No Network Address Translation (NAT). It can be achieved with:
	- - [Weave](https://www.weave.works/oss/net/)
	- [Flannel](https://github.com/flannel-io/flannel#flannel)
	- [Calico](https://www.projectcalico.org/)
	- [Cilium](https://cilium.io/).
For more information see the ["Cluster Networking"](https://kubernetes.io/docs/concepts/cluster-administration/networking/)
## External-to-Pod Communication
Kubernetes provides external accessibility through **Services**, which are sophisticated collections of network routing rules. These rules are stored in **iptables** on cluster nodes and executed by **kube-proxy** agents. By using **kube-proxy** to expose services, applications can be accessed from outside the cluster using a virtual IP address and a specific port number. This allows external users to interact with the applications hosted within the cluster.

The service object is used to connect to the Pods using:
	- in cluster: ClusterIP,
	- from outside of the cluster: NodePort or Load Balancer

[[2023100716443333 K8s Service network flow]]
1. LinuxFoundationX LFS158x. Chapter 4. Kubernetes Architecture
2. https://trainingportal.linuxfoundation.org/courses/kubernetes-for-developers-lfd259 Kubernetes Architecture