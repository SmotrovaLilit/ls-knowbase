# Arbitrary strings

## [Annotations](https://kubernetes.io/docs/concepts/overview/working-with-objects/annotations/)

Is used for:
- Store git branch, build/release IDs, PR numbers, etc.
- Phones of people responsible
- Ingress controller information
- Revision number
- Deployment state
- Pointers to monitoring, logging, audit repositories, debugging tools
## Taints
Nodes may have taints. It is an arbitrary string in the node metadata. It needs to inform the scheduler on Pod assignments used along with toleration in Pod metadata, indicating it should be scheduled on a node with the particular taint.

## References
 1. https://trainingportal.linuxfoundation.org/courses/kubernetes-for-developers-lfd259 Kubernetes Architecture
 2. LinuxFoundationX LFS158x.1. Chapter 15. [Advanced Topics](https://learning.edx.org/course/course-v1:LinuxFoundationX+LFS158x+1T2022/block-v1:LinuxFoundationX+LFS158x+1T2022+type@sequential+block@a99776b812ed450593b771883452d76c)
 3. 
 



 