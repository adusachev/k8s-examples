

Apply configs:

```sh
kubectl apply -f nginx-pvc.yaml
```

```sh
kubectl apply -f nginx-configmap.yaml
```

```sh
kubectl apply -f nginx-deployment.yaml
```


Create some file:
```sh
kubectl exec -it fileshare-<POD_ID> -- bash
cd /data
echo "lol kek" > my-file.txt
```

Check:
```sh
kubectl port-forward pod/fileshare-<POD_ID> 7080:80 --address='0.0.0.0'
curl localhost:7080/files/
```










