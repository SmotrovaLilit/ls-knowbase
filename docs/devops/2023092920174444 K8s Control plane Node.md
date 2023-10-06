# Control plane Node
"A control plane node serves as the execution environment for control plane agents, which are responsible for overseeing the Kubernetes cluster's state. Losing the control plane could result in downtime. To enhance availability, you can add replicas of control plane nodes to the cluster, enabling High Availability mode

All cluster configuration data is saved to distributed key-value store independently with client workload data. 

###  Control Plane Node Components
- API Server(**kube-apiserver**)
	- can be scale horizontally
	- supports addition of custom  API Servers
- Scheduler( **kube-scheduler**)
	-  highly configurable and customizable through plugins, scheduling policies, and profiles.
	- supports addition of custom schedulers
- Controller Managers
	-  The **kube-controller-manager** operates controllers or operators that respond to various events such as node unavailability, ensuring the desired container pod counts, and creating endpoints, service accounts, and API access tokens when needed.
	-   The **cloud-controller-manager** operates controllers or operators that handle interactions with the cloud provider's infrastructure. These controllers manage tasks such as handling node unavailability, managing storage volumes provided by a cloud service, and overseeing load balancing and routing.
- Key-Value Data Store [**etcd**](https://etcd.io/)
	-  only the API Server is able to communicate with the etcd data store.
	- **etcdctl** - etcd's CLI management tool.
	- etcd is based on the [Raft Consensus Algorithm](https://web.stanford.edu/~ouster/cgi-bin/papers/raft-atc14) which allows a collection of machines to work as a coherent group that can survive the failures of some of its members.
	- etcd is also used to store configuration details such as subnets, ConfigMaps, Secrets, etc.
	- [[2023092918361010 Stacked and external  etcd topologies]]
- Container Runtime
- Node Agent
- Proxy
- Optional add-ons for cluster-level monitoring and logging.

## References
1. LinuxFoundationX LFS158x. Chapter 4. Kubernetes Architecture