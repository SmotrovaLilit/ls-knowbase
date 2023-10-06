## APIs:
- /api/v1 - core group:  Pods, Services, Nodes, Namespaces, ConfigMaps, Secrets, etc
- **/apis/\$NAME/\$VERSION** - named group
- system-wide: **/healthz**, **/logs**, **/metrics**, **/ui**, etc
Access to API server:
- CLI tools
- Dashboard UI
- Calling API endpoints

## **kubectl**
Allows to manage Kubernetes clusters. 
Details here [kubectl book](https://kubectl.docs.kubernetes.io/), the [Kubernetes official documentation](https://kubernetes.io/docs/reference/kubectl/), or its [GitHub repository](https://github.com/kubernetes/kubectl).
###  Installing kubectl on macOS
[install](https://kubernetes.io/docs/tasks/tools/install-kubectl-macos/)

```bash
kubectl config view
```

```bash
kubectl cluster-info
```

## Kubernetes Dashboard
- it is addon
- disabled by default.

```bash
minikube addons list
```

```bash
minikube addons enable metrics-server
```

```bash
minikube addons enable dashboard
```

```bash
minikube dashboard
```

##  APIs with 'kubectl proxy'
```bash
 kubectl proxy &
```

```bash
curl http://localhost:8001/
```

## Authentication

Let's get request without kubectl proxy.
```bash
export TOKEN=$(kubectl create token default)
```

```bash
kubectl create clusterrole api-access-root --verb=get --non-resource-url="/*"
```

```bash
kubectl create clusterrolebinding api-access-root --clusterrole api-access-root --serviceaccount=default:default
```

```bash
export APISERVER=$(kubectl config view | grep https | cut -f 2- -d ":" | tr -d " ")
```

```bash
curl $APISERVER --header "Authorization:** **Bearer $TOKEN" --insecure
```
Or you can use authentication with certificate:
```bash
curl $APISERVER --cert encoded-cert --key encoded-key --cacert encoded-ca
```
## References
1. LinuxFoundationX LFS158x.1. [Chapter 7. Accessing Minikube](https://learning.edx.org/course/course-v1:LinuxFoundationX+LFS158x+1T2022/block-v1:LinuxFoundationX+LFS158x+1T2022+type@sequential+block@815c1eb1ffb24a7b80bbf9df6d6a3267)
2. 