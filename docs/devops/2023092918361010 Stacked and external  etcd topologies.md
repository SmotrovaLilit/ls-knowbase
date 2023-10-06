# Stacked and external  etcd topologies

![[Pasted image 20230929183149.png]]
The data store operates in conjunction with other control plane components, sharing resources within the same control plane node

![[Pasted image 20230929183224.png]]
To ensure data store isolation from the control plane components, you can configure the bootstrapping process to use an external etcd topology. In this setup, the data store is provisioned on a dedicated host, reducing the risk of an etcd failure impacting other components.

## References
1. LinuxFoundationX LFS158x. Chapter 4. Kubernetes Architecture