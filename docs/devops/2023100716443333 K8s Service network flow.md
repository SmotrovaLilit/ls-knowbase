# K8s service network flow

How to communicate with pod:
- an ingress controller or service mesh [[2023100716252828 Service Mesh]] like Istio
- Services with type  Cluster IP - available only in the cluster.  svc2 on the picture
- Services with type  NodePort or load balancer - available outside from the cluster.  svc1 on the picture
![[Pasted image 20231007164436.png]]

## References
1. https://trainingportal.linuxfoundation.org/courses/kubernetes-for-developers-lfd259 Kubernetes Architecture
2. https://speakerdeck.com/thockin/illustrated-guide-to-kubernetes-networking