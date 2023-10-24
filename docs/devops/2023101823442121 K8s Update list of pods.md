# K8s Update list of pods

```bash
for name in try1-6f6694b4b-58nqf try1-6f6694b4b-5hlh6 try1-6f6694b4b-n9mhd try1-6f6694b4b-rpzgf try1-6f6694b4b-zwgxf; do  kubectl exec $name -- touch /tmp/healthy; done
```
