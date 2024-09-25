
**Step 1**

Login to your private registry (GitLab example):
```sh
docker login registry.gitlab.com
```
// auth stored in `~/.docker/config.json`

Build some image:
```sh
docker build -t registry.gitlab.com/test-group5525628/my-registry:<TAG_NAME> .
```

Push builded image to registry:
```sh
docker push registry.gitlab.com/test-group5525628/my-registry:<TAG_NAME>
```

**Step 2**

```sh
cat ~/.docker/config.json | base64
```
// add result to docker-secret.yaml

```sh
kubectl apply -f docker-secret.yaml
```

**Step 3**

Create Deployment:
```sh
kubectl apply -f my-app-deployment.yaml
```

Check logs:
```sh
kubectl logs <POD_NAME>
```

```sh
kubectl describe pod <POD_NAME>
```
