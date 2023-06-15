# nginxic-manifests

- https://docs.nginx.com/nginx-ingress-controller/installation/installation-with-manifests/

```
git clone https://github.com/nginxinc/kubernetes-ingress.git --branch v3.1.1
cd kubernetes-ingress/deployments
```

```
kubectl apply -f common/ns-and-sa.yaml
kubectl apply -f rbac/rbac.yaml
kubectl apply -f rbac/ap-rbac.yaml
kubectl apply -f rbac/apdos-rbac.yaml
```
export nginx_ingress=$(kubectl get svc nginx-ingress --namespace=nginx-ingress | tr -s " " | cut -d' ' -f4 | grep -v "EXTERNAL-IP")
