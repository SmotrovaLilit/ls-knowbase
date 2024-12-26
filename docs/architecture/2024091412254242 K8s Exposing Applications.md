# K8s Exposing Applications
## Service Types [Service](https://kubernetes.io/docs/concepts/services-networking/service/)
- ClusterIP - internal access. Use kubectl proxy for troubleshooting and development work
- NodePort -  access from outside of cluster. Uses for debugging, or when a static IP address is needed, for example opening a particular address through a firewall.
- LoadBalancer- was created to pass requests to a cloud provider like GKE or AWS
- ExternalName- is not used as much, as CoreDNS has become more stable.

The kube-proxy mode is configured via a flag sent during initialization, such as **mode=iptables** and could also be **ipvs** or **userspace**.