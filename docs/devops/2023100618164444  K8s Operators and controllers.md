# Operators and controllers

Operators and controllers are watch-loops, that get the current state, compare it against the spec, and execute code based on how they differ.
- Deployment [[2023100413063636 K8s Deployment]]
- ReplicaSet [[2023100413063232 K8s ReplicaSet]]
- Jobs and CronJobs  to handle single or recurring tasks
- DaemonSet [[2023100413064141 K8s DaemonSet]]
- StatefulSet - to deploy pods in a particular order, such that following pods are only deployed if previous pods report a ready status.
- You can create your own controller as well

## References
 1. https://trainingportal.linuxfoundation.org/courses/kubernetes-for-developers-lfd259 Kubernetes Architecture