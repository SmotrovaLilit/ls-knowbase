
# Delete docker images

```bash
docker images | grep "mock" | awk '{print $1}' | xargs docker rmi
```