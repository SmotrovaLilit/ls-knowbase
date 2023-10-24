# Kubernetes Architecture
High-level architecture diagram of the K8s components

![[Pasted image 20231006181212.png]]

[[2023092920174444 K8s Control plane Node]]
[[2023092920181919 K8s Worker node]]
[[2023092920304040 K8s Networking Challenges]]
## Configuration
- Saved in json format
- Usually users used YAML format, Kubernetes agents convert the YAML to JSON prior to persistence to the database.

## Container creation and management.
Buildah, Podman, containerd

## Challenges
-  continuous integration pipeline
- cluster of machines
-  you must be able to perform rolling updates and rollbacks
-  tear down the resource when no longer needed
-  flexible, scalable, and easy-to-manage network and storage
## References
1. LinuxFoundationX LFS158x. Chapter 4. Kubernetes Architecture
2. https://trainingportal.linuxfoundation.org/courses/kubernetes-for-developers-lfd259 Kubernetes Architecture