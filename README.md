## Documentation for Setup ArgoCD
https://github.com/argoproj/argo-cd/releases

## Installation and Update
```bash
# Install
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/v2.3.7/manifests/install.yaml

# Update
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/v2.4.8/manifests/install.yaml
```

## Access ArgoCD API with port-forward **
````bash
# Port forward
kubectl port-forward svc/argocd-server -n argocd 8080:443

# Get admin password
kubectl get secret -n argocd argocd-initial-admin-secret  -o yaml
echo "WGZQdkNXREI3SVUzLTFtZA==" | base64 --decode
````

## Deploy the first application. Connect Kubernetes with Git repository
```bash
# Connect Git with kubernetes
kubectl apply -f application.yaml -n argocd
```
